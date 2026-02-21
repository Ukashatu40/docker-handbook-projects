# Using 3.12 for stability (3.14 is still experimental)
FROM python:3.12-alpine

WORKDIR /zone

RUN apk add --no-cache git && \
    git clone https://github.com/fhsinchy/rmbyext.git /tmp/rmbyext && \
    # Remove the test module/folder so setuptools doesn't get confused
    rm -rf /tmp/rmbyext/test_rmbyext* && \
    pip install /tmp/rmbyext && \
    rm -rf /tmp/rmbyext && \
    apk del git

# (Add your ENTRYPOINT or CMD here)

ENTRYPOINT [ "rmbyext" ]