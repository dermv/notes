# ──────────────────────────────────────────────────────────────
#  Published notes · Quartz output served by unprivileged Angie
#
#  Build context: the generated public/ folder.
#  Named context "deploy": this folder, for angie.conf.
# ──────────────────────────────────────────────────────────────

FROM docker.angie.software/angie:minimal

RUN rm -rf /usr/share/angie/html/*

COPY --from=deploy angie.conf /etc/angie/angie.conf
COPY . /usr/share/angie/html/

USER angie
EXPOSE 8080

CMD ["angie", "-e", "stderr", "-g", "daemon off;"]
