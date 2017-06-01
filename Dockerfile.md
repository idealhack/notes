# Dockerfile


## Example

### Ubuntu

    FROM ubuntu
    LABEL maintainer idealhack@gmail.com
    RUN sed -i 's/http:\/\/archive\.ubuntu\.com\/ubuntu\//http:\/\/mirrors\.163\.com\/ubuntu\//g' /etc/apt/sources.list && \
        apt-get update && apt-get install -y --no-install-recommends \
            tzdata \
        && apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

    RUN echo Asia/Shanghai > /etc/timezone && \
        ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
        dpkg-reconfigure -f noninteractive tzdata


### Nginx

    FROM nginx
    LABEL maintainer idealhack@gmail.com
    RUN sed -i 's/deb\.debian\.org/mirrors\.163\.com/g' /etc/apt/sources.list && \
        apt-get update && apt-get install -y --no-install-recommends \
            tzdata \
            ffmpeg \
        && apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

    RUN echo Asia/Shanghai > /etc/timezone && \
        ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
        dpkg-reconfigure -f noninteractive tzdata


## Resources

- http://www.johnzaccone.io/entrypoint-vs-cmd-back-to-basics/
