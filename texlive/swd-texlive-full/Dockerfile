FROM debian:buster-slim

ENV PATH $PATH:/usr/local/texlive/2020/bin/x86_64-linux

RUN apt update \
 && apt install --assume-yes --no-install-recommends \
      build-essential \
      texlive-full \
      python3-pygments \
      fonts-noto-cjk \
      fonts-noto-cjk-extra \
      libfontconfig-dev \
      ghostscript \
 && mkdir -p /usr/local/texlive/texmf-local/fonts/opentype/google/notosanscjk/ \
 && mkdir -p /usr/local/texlive/texmf-local/fonts/opentype/google/notoserifcjk/ \
 && ln -s /usr/share/fonts/opentype/noto/NotoSansCJK-*.ttc \
             /usr/local/texlive/texmf-local/fonts/opentype/google/notosanscjk/ \
 && ln -s /usr/share/fonts/opentype/noto/NotoSerifCJK-*.ttc \
             /usr/local/texlive/texmf-local/fonts/opentype/google/notoserifcjk/ \
 && mktexlsr \
 && apt purge -y libfontconfig-dev \
 && apt autoremove -y \
 && rm -rf /var/lib/apt/lists/*

RUN mkdir /tex_src

VOLUME /tex_src

WORKDIR /tex_src

CMD ["/bin/bash"]


