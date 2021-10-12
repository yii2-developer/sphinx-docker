FROM alpine:3

RUN wget https://sphinxsearch.com/files/sphinx-3.4.1-efbcc65-linux-amd64.tar.gz -O /tmp/sphinx.tar.gz \
	&& cd /opt && tar -xf /tmp/sphinx.tar.gz \
	&& rm /tmp/sphinx.tar.gz

RUN mkdir -p /opt/sphinx-3.4.1/data

COPY sphinx.conf /opt/sphinx-3.4.1/sphinx.conf

ENV PATH "${PATH}:/opt/sphinx-3.4.1/bin"

CMD ["searchd", "--config", "/opt/sphinx-3.4.1/sphinx.conf", "--nodetach"]
