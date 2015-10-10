FROM python:2
RUN pip install --no-cache-dir ZODB3==3.10.5 && \
(python -m compileall -q /usr/local/lib/python2.7 || true)

VOLUME /var/lib/zeo
CMD ["runzeo", "-a", "9675", "-f", "/var/lib/zeo/Data.fs"]
EXPOSE 9675
