FROM solr:9.8.1


USER root
# Set your custom Solr home
ENV SOLR_HOME=/data/586d04e0-9f72-4754-976b-6b5ff6009f1c/3db9497d-2052-4c52-a6fd-c7854f72ec0f

COPY --chown=solr:solr scripts /opt/docker-solr/scripts
COPY --chown=solr:solr bankrule /var/solr/data/bankrule
RUN mkdir -p /var/solr/move/bankrule
    
    RUN chmod -R 0777 /var/solr/data && \
    chmod -R 0777 /var/solr/move && \
    chmod -R +x /opt/docker-solr/scripts
    
VOLUME /var/solr
EXPOSE 8983
WORKDIR /opt/solr
USER $SOLR_UID

ENTRYPOINT ["docker-entrypoint.sh"]
CMD ["solr-foreground"]
