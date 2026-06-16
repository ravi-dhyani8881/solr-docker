FROM solr:9.8.1


USER root
# Set your custom Solr home
ENV SOLR_HOME=/data/baaa5a57-1f2e-48bd-95a4-9103c847a98a/9317dd5e-4641-4ed6-ac0c-54f3f7636e6d

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
