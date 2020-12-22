FROM alpine:3

RUN wget http://sphinxsearch.com/files/sphinx-3.3.1-b72d67b-linux-amd64-musl.tar.gz -O /tmp/sphinx.tar.gz \
	&& cd /opt && tar -xf /tmp/sphinx.tar.gz \
	&& rm /tmp/sphinx.tar.gz

RUN mkdir -p /opt/sphinx-3.3.1/data

COPY sphinx.conf /opt/sphinx-3.3.1/sphinx.conf

ENV PATH "${PATH}:/opt/sphinx-3.3.1/bin"

CMD ["searchd", "--config", "/opt/sphinx-3.3.1/sphinx.conf", "--nodetach"]
