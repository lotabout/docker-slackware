FROM vbatts/slackware

# install slapt-get
RUN wget http://software.jaos.org/slackpacks/14.2-x86_64/slapt-get/slapt-get-0.10.2s-x86_64-1.tgz && installpkg slapt-get-0.10.2s-x86_64-1.tgz && rm slapt-get-0.10.2s-x86_64-1.tgz

# install dependencies
RUN slackpkg update gpg && slackpkg update && slackpkg install gpgme libassuan libgpg-error cyrus-sasl && rm -rf /var/lib/slackpkg

# change the repos to current
RUN sed -i 's/slackware64-14.1/slackware64-current/' /etc/slapt-get/slapt-getrc

# add repository: http://packages.slackonly.com/
RUN echo "SOURCE=http://packages.slackonly.com/pub/packages/current-x86_64/:DEFAULT" >> /etc/slapt-get/slapt-getrc

# to use slapt-get
# slapt-get -u
# slapt-get -i <package-name>
# rm -rf /var/slapt-get # to clean up the cache
