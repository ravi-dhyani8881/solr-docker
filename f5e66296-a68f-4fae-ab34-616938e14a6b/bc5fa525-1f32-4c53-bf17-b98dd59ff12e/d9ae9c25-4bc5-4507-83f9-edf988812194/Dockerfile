FROM solr:9.8.1


USER root
# Set your custom Solr home
ENV SOLR_HOME=/data/d9ae9c25-4bc5-4507-83f9-edf988812194/bd1780bb-5416-460f-b58c-9c42d80d977b

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
