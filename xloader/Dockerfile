FROM ckan/ckan-base-xloader:1.0.1

RUN pip3 install -e 'git+https://github.com/keitaroinc/ckanext-c3charts.git@master#egg=ckanext-c3charts'
RUN pip3 install -e 'git+https://github.com/handryanp/ckanext-temabaru@main#egg=ckanext-temabaru'

# Set up environment variables
ENV APP_DIR=/srv/app
ENV TZ=UTC
RUN echo ${TZ} > /etc/timezone

# Make sure both files are not exactly the same
RUN if ! [ /usr/share/zoneinfo/${TZ} -ef /etc/localtime ]; then \
        cp /usr/share/zoneinfo/${TZ} /etc/localtime ;\
    fi ;

EXPOSE 5000
