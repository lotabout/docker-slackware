FROM lotabout/slackware-slapt-get

RUN slapt-get -u \
    && slapt-get -i python python-setuptools pip libffi python3\
    && rm -rf /var/slapt-get

# install pip3
# modified from https://slackbuilds.org/repository/14.1/python/pip/
RUN cd /tmp; \
    wget --no-check-certificate https://slackbuilds.org/slackbuilds/14.1/python/pip.tar.gz; \
    tar xf pip.tar.gz; \
    cd /tmp/pip; \
    sed -i 's/pip/pip3/;s/python/python3/;/^cd/s/PRGNAM/{PRGNAM%3}/' pip.SlackBuild; \
    wget --no-check-certificate https://pypi.python.org/packages/source/p/pip/pip-7.1.2.tar.gz; \
    for file in pip*; do mv $file ${file/#pip/pip3}; done; \
    bash pip3.SlackBuild; \
    installpkg /tmp/pip3-7.1.2-x86_64-1_SBo.tgz; \
    rm -rf /tmp/*;
