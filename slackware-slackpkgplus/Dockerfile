FROM vbatts/slackware

# gcc
# http://ufpr.dl.sourceforge.net/project/slackpkgplus/slackpkg%2B-1.6.1p2-noarch-2mt.txz
RUN wget http://ufpr.dl.sourceforge.net/project/slackpkgplus/slackpkg%2B-1.6.1p2-noarch-2mt.txz
RUN installpkg slackpkg+-1.6.1p2-noarch-2mt.txz && rm slackpkg+-1.6.1p2-noarch-2mt.txz
RUN slackpkg update gpg
RUN slackpkg update
