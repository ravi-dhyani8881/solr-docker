FROM solr:9.8.1


USER root
# Set your custom Solr home
ENV SOLR_HOME=/data/d9ae9c25-4bc5-4507-83f9-edf988812194/eda6fdf3-7103-44e4-8567-add0f472f0f8

COPY --chown=solr:solr scripts /opt/docker-solr/scripts
COPY --chown=solr:solr orders /var/solr/data/orders
RUN mkdir -p /var/solr/move/orders
COPY --chown=solr:solr Supply /var/solr/data/Supply
RUN mkdir -p /var/solr/move/Supply
COPY --chown=solr:solr users /var/solr/data/users
RUN mkdir -p /var/solr/move/users
COPY --chown=solr:solr user /var/solr/data/user
RUN mkdir -p /var/solr/move/user
    
    RUN chmod -R 0777 /var/solr/data && \
    chmod -R 0777 /var/solr/move && \
    chmod -R +x /opt/docker-solr/scripts
    
VOLUME /var/solr
EXPOSE 8983
WORKDIR /opt/solr
USER $SOLR_UID

ENTRYPOINT ["docker-entrypoint.sh"]
CMD ["solr-foreground"]
