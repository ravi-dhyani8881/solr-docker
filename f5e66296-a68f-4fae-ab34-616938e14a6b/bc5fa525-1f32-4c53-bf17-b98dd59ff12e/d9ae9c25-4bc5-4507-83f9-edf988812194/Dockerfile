FROM solr:9.8.1


USER root
# Set your custom Solr home
ENV SOLR_HOME=/data/d9ae9c25-4bc5-4507-83f9-edf988812194/ff80ae7e-0b37-4173-a9cc-642cdb45f75c

COPY --chown=solr:solr scripts /opt/docker-solr/scripts
COPY --chown=solr:solr orders /var/solr/data/orders
RUN mkdir -p /var/solr/move/orders
COPY --chown=solr:solr Supply /var/solr/data/Supply
RUN mkdir -p /var/solr/move/Supply
    
    RUN chmod -R 0777 /var/solr/data && \
    chmod -R 0777 /var/solr/move && \
    chmod -R +x /opt/docker-solr/scripts
    
VOLUME /var/solr
EXPOSE 8983
WORKDIR /opt/solr
USER $SOLR_UID

ENTRYPOINT ["docker-entrypoint.sh"]
CMD ["solr-foreground"]
