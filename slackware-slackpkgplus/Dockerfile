FROM vbatts/slackware

# install slackpkg+
# http://ufpr.dl.sourceforge.net/project/slackpkgplus/slackpkg%2B-1.6.1p2-noarch-2mt.txz
# should put the commands in oneline so that the 'rm' command will take effect
RUN wget http://ufpr.dl.sourceforge.net/project/slackpkgplus/slackpkg%2B-1.6.1p2-noarch-2mt.txz && installpkg slackpkg+-1.6.1p2-noarch-2mt.txz && rm slackpkg+-1.6.1p2-noarch-2mt.txz

# add repository: http://packages.slackonly.com/
RUN echo "MIRRORPLUS['slackonly']=http://slackonly.com/pub/packages/current-x86_64/" >> /etc/slackpkg/slackpkgplus.conf
RUN sed -i '/^REPOPLUS/s/)/slackonly )/' /etc/slackpkg/slackpkgplus.conf

# If your dockerfile based on this one, please add the following two commands
# RUN slackpkg update gpg
# RUN slackpkg update
