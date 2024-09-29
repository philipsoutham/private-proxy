FROM alpine:3.20

RUN apk --no-cache --update --upgrade add privoxy

RUN mv /etc/privoxy/config.new /etc/privoxy/config \
    && mv /etc/privoxy/default.action.new /etc/privoxy/default.action \
    && mv /etc/privoxy/user.action.new /etc/privoxy/user.action \
    && mv /etc/privoxy/default.filter.new /etc/privoxy/default.filter \
    && mv /etc/privoxy/user.filter.new /etc/privoxy/user.filter \
    && mv /etc/privoxy/regression-tests.action.new /etc/privoxy/regression-tests.action \
    && mv /etc/privoxy/trust.new /etc/privoxy/trust \
    && mv /etc/privoxy/match-all.action.new /etc/privoxy/match-all.action\
    && echo "forward-socks5t / 172.18.0.5:9050 ." >> /etc/privoxy/config \
    && sed -i 's/listen-address\s*127.0.0.1:8118/listen-address 0.0.0.0:8118/g' /etc/privoxy/config


USER privoxy

ENTRYPOINT ["privoxy"]
CMD [ "--no-daemon", "/etc/privoxy/config" ]
