FROM alpine:3.20

RUN apk --no-cache --update --upgrade add tor nyx

USER tor

ENTRYPOINT ["tor"]
CMD ["-f", "/etc/tor/torrc"]
