FROM debian:latest

RUN apt update \
 && apt --auto-remove purge npm nodejs \
 && apt install --assume-yes --no-install-recommends nodejs npm \
 && npm install --global npm@latest \
 && npm install --global firebase-tools \
 && apt autoremove -y \
 && rm -rf /var/lib/apt/lists/*

CMD ["/bin/bash"]


