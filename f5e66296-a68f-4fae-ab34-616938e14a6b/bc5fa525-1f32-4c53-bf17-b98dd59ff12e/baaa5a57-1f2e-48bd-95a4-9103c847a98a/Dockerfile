FROM solr:9.8.1


USER root
# Set your custom Solr home
ENV SOLR_HOME=/data/baaa5a57-1f2e-48bd-95a4-9103c847a98a/aeab4d13-2631-4328-b60d-9071f88078ef

COPY --chown=solr:solr scripts /opt/docker-solr/scripts
COPY --chown=solr:solr orders /var/solr/data/orders
RUN mkdir -p /var/solr/move/orders
COPY --chown=solr:solr users /var/solr/data/users
RUN mkdir -p /var/solr/move/users
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
