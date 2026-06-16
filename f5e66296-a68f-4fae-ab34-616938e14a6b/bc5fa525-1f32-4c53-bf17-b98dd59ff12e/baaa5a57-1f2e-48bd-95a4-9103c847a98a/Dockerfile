FROM solr:9.8.1


USER root
# Set your custom Solr home
ENV SOLR_HOME=/data/baaa5a57-1f2e-48bd-95a4-9103c847a98a/85be27a5-b73c-484a-909c-aacc2c914ce4

COPY --chown=solr:solr scripts /opt/docker-solr/scripts
COPY --chown=solr:solr orders /var/solr/data/orders
RUN mkdir -p /var/solr/move/orders
COPY --chown=solr:solr user /var/solr/data/user
RUN mkdir -p /var/solr/move/user
COPY --chown=solr:solr supply /var/solr/data/supply
RUN mkdir -p /var/solr/move/supply
    
    RUN chmod -R 0777 /var/solr/data && \
    chmod -R 0777 /var/solr/move && \
    chmod -R +x /opt/docker-solr/scripts
    
VOLUME /var/solr
EXPOSE 8983
WORKDIR /opt/solr
USER $SOLR_UID

ENTRYPOINT ["docker-entrypoint.sh"]
CMD ["solr-foreground"]
