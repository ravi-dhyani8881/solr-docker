FROM solr:9.8.1


USER root
# Set your custom Solr home
ENV SOLR_HOME=/data/8d5d2c0f-5447-4ad5-889b-75e5d7a3a35f/aa7098b5-0f03-4f41-bb10-db9a919a52eb

COPY --chown=solr:solr scripts /opt/docker-solr/scripts
COPY --chown=solr:solr reviews /var/solr/data/reviews
RUN mkdir -p /var/solr/move/reviews
COPY --chown=solr:solr products /var/solr/data/products
RUN mkdir -p /var/solr/move/products
COPY --chown=solr:solr ratings /var/solr/data/ratings
RUN mkdir -p /var/solr/move/ratings
    
    RUN chmod -R 0777 /var/solr/data && \
    chmod -R 0777 /var/solr/move && \
    chmod -R +x /opt/docker-solr/scripts
    
VOLUME /var/solr
EXPOSE 8983
WORKDIR /opt/solr
USER $SOLR_UID

ENTRYPOINT ["docker-entrypoint.sh"]
CMD ["solr-foreground"]
