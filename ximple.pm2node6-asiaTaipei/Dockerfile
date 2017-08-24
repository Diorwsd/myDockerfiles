FROM node:6.11.2-slim
LABEL maintainer="diorwsd <diorwsd@ximple.com.tw>"

#時區設定 Asia/Taipei
ENV TZ=Asia/Taipei
# RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN cp /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN npm install pm2 -g

VOLUME ["/app"]

# Expose ports
EXPOSE 80 443 43554

WORKDIR /app

# Start process.yml
CMD ["pm2-docker", "start", "--auto-exit", "--env", "production", "process.yml"]
