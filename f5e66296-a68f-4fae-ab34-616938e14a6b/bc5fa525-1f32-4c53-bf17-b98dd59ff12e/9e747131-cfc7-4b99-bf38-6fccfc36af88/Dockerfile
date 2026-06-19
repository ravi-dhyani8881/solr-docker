FROM solr:9.8.1


USER root
# Set your custom Solr home
ENV SOLR_HOME=/data/9e747131-cfc7-4b99-bf38-6fccfc36af88/c200e174-f5a6-44d3-8344-c4df610b9d8c

COPY --chown=solr:solr scripts /opt/docker-solr/scripts
COPY --chown=solr:solr content /var/solr/data/content
RUN mkdir -p /var/solr/move/content
COPY --chown=solr:solr user /var/solr/data/user
RUN mkdir -p /var/solr/move/user
COPY --chown=solr:solr review /var/solr/data/review
RUN mkdir -p /var/solr/move/review
COPY --chown=solr:solr like /var/solr/data/like
RUN mkdir -p /var/solr/move/like
COPY --chown=solr:solr helpfull /var/solr/data/helpfull
RUN mkdir -p /var/solr/move/helpfull
COPY --chown=solr:solr dislike /var/solr/data/dislike
RUN mkdir -p /var/solr/move/dislike
COPY --chown=solr:solr reply /var/solr/data/reply
RUN mkdir -p /var/solr/move/reply
    
    RUN chmod -R 0777 /var/solr/data && \
    chmod -R 0777 /var/solr/move && \
    chmod -R +x /opt/docker-solr/scripts
    
VOLUME /var/solr
EXPOSE 8983
WORKDIR /opt/solr
USER $SOLR_UID

ENTRYPOINT ["docker-entrypoint.sh"]
CMD ["solr-foreground"]
