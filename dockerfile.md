FROM n8nio/n8n:latest

USER root

ENV PIP_NO_CACHE_DIR=1 \

NODE_ENV=production

# Instala dependências do sistema para FFmpeg, Python, GraphicsMagick

RUN apk add --no-cache \

ffmpeg python3 py3-pip curl graphicsmagick \

font-dejavu ttf-dejavu

# Instala yt-dlp

RUN curl -L [https://github.com/yt-dlp/yt-dlp/releases/latest/download/yt-dlp](https://github.com/yt-dlp/yt-dlp/releases/latest/download/yt-dlp) \

-o /usr/local/bin/yt-dlp && chmod a+rx /usr/local/bin/yt-dlp

# Instala libs Python extras

RUN pip3 install --break-system-packages --no-cache-dir \

yt-dlp instaloader requests

# (Opcional) Força uso do npm

RUN npm install -g only-allow && only-allow npm

# Instala apenas os community nodes necessários em /data

WORKDIR /data

RUN npm install --omit=dev --no-audit --no-fund --only=production \

n8n-nodes-evolution-api \

n8n-nodes-cloudconvert

# Testes rápidos (verifica se tudo instalou)

RUN yt-dlp --version \

&& ffmpeg -version \

&& gm version \

&& python3 -c "import instaloader, requests; print('Python libs OK')" \

&& node -e "console.log('Node.js OK')"

USER node
