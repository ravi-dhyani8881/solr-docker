FROM solr:9.8.1


USER root
# Set your custom Solr home
ENV SOLR_HOME=/data/bb88b8bf-63b3-452e-ad73-c3b849f54995/6b2273ee-92f6-45d2-b731-fa95e1cde686

COPY --chown=solr:solr scripts /opt/docker-solr/scripts
COPY --chown=solr:solr bus_routes /var/solr/data/bus_routes
RUN mkdir -p /var/solr/move/bus_routes
COPY --chown=solr:solr stops /var/solr/data/stops
RUN mkdir -p /var/solr/move/stops
COPY --chown=solr:solr routes_stops /var/solr/data/routes_stops
RUN mkdir -p /var/solr/move/routes_stops
    
    RUN chmod -R 0777 /var/solr/data && \
    chmod -R 0777 /var/solr/move && \
    chmod -R +x /opt/docker-solr/scripts
    
VOLUME /var/solr
EXPOSE 8983
WORKDIR /opt/solr
USER $SOLR_UID

ENTRYPOINT ["docker-entrypoint.sh"]
CMD ["solr-foreground"]
