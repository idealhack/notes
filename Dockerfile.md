# Dockerfile


## Example

    FROM ubuntu
    LABEL maintainer idealhack@gmail.com
    RUN sed -i 's/http:\/\/archive\.ubuntu\.com\/ubuntu\//http:\/\/mirrors\.163\.com\/ubuntu\//g' /etc/apt/sources.list && \
        apt-get update && apt-get install -y --no-install-recommends \
            tzdata  \
        && apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

    RUN echo Asia/Shanghai > /etc/timezone && \
        ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
        dpkg-reconfigure -f noninteractive tzdata
