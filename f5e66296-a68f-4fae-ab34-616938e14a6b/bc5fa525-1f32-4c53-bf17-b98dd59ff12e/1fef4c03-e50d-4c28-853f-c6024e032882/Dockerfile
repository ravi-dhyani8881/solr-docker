FROM solr:9.8.1


USER root
# Set your custom Solr home
ENV SOLR_HOME=/data/1fef4c03-e50d-4c28-853f-c6024e032882/604ec87e-0669-49e8-8b58-05c209118e1f

COPY --chown=solr:solr scripts /opt/docker-solr/scripts
COPY --chown=solr:solr User /var/solr/data/User
RUN mkdir -p /var/solr/move/User
    
    RUN chmod -R 0777 /var/solr/data && \
    chmod -R 0777 /var/solr/move && \
    chmod -R +x /opt/docker-solr/scripts
    
VOLUME /var/solr
EXPOSE 8983
WORKDIR /opt/solr
USER $SOLR_UID

ENTRYPOINT ["docker-entrypoint.sh"]
CMD ["solr-foreground"]
