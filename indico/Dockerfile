FROM python:2.7.10
RUN mkdir -p /usr/src && \
cd /usr/src && \
curl -LJO https://github.com/XeCycle/indico/releases/download/dist-f6777a9/requirements.txt && \
curl -LJO https://github.com/XeCycle/indico/releases/download/dist-f6777a9/indico-1.9.6-py2.7.egg && \
pip install --no-cache-dir -r requirements.txt && \
easy_install indico-1.9.6-py2.7.egg && \
pip install --no-cache-dir uwsgi && \
cd / && \
rm -r /usr/src /tmp/* && \
cp /usr/local/lib/python2.7/site-packages/indico-1.9.6-py2.7.egg/indico/web/indico.wsgi / && \
sed -i 's|indico_conf = ""|indico_conf = "/etc/indico.conf"|' /usr/local/lib/python2.7/site-packages/indico-1.9.6-py2.7.egg/MaKaC/common/MaKaCConfig.py && \
(python -m compileall -q /usr/local/lib/python2.7 || true)

COPY indico.conf /etc/

VOLUME /opt/indico
VOLUME /usr/local/lib/python2.7/site-packages/indico-1.9.6-py2.7.egg/htdocs/static/assets

EXPOSE 80

CMD ["uwsgi", "--http", ":80", "--wsgi-file", "/indico.wsgi"]
