FROM vbatts/slackware

# install slapt-get
RUN wget http://software.jaos.org/slackpacks/14.2-x86_64/slapt-get/slapt-get-0.10.2s-x86_64-1.tgz
RUN installpkg slapt-get-0.10.2s-x86_64-1.tgz && rm slapt-get-0.10.2s-x86_64-1.tgz

RUN slackpkg update gpg
RUN slackpkg update

# install dependencies
RUN slackpkg install gpgme libassuan libgpg-error cyrus-sasl

# add repository: http://packages.slackonly.com/
RUN echo "SOURCE=http://packages.slackonly.com/pub/packages/current-x86_64/:DEFAULT" >> /etc/slapt-get/slapt-getrc

# to use slapt-get
# slapt-get -u
# slapt-get -i <package-name>
