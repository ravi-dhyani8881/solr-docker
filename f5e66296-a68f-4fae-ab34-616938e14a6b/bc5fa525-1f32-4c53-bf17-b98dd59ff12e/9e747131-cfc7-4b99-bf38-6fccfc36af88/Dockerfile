FROM solr:9.8.1


USER root
# Set your custom Solr home
ENV SOLR_HOME=/data/9e747131-cfc7-4b99-bf38-6fccfc36af88/4ec9e601-c391-41e7-822b-0abbfbbdb77f

COPY --chown=solr:solr scripts /opt/docker-solr/scripts
COPY --chown=solr:solr users /var/solr/data/users
RUN mkdir -p /var/solr/move/users
COPY --chown=solr:solr products /var/solr/data/products
RUN mkdir -p /var/solr/move/products
COPY --chown=solr:solr reviews /var/solr/data/reviews
RUN mkdir -p /var/solr/move/reviews
COPY --chown=solr:solr review_responses /var/solr/data/review_responses
RUN mkdir -p /var/solr/move/review_responses
    
    RUN chmod -R 0777 /var/solr/data && \
    chmod -R 0777 /var/solr/move && \
    chmod -R +x /opt/docker-solr/scripts
    
VOLUME /var/solr
EXPOSE 8983
WORKDIR /opt/solr
USER $SOLR_UID

ENTRYPOINT ["docker-entrypoint.sh"]
CMD ["solr-foreground"]
