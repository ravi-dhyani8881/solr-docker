FROM solr:9.8.1


USER root
# Set your custom Solr home
ENV SOLR_HOME=/data/9dd0c8bf-0a27-4293-9442-db5b86a7c07f/

COPY --chown=solr:solr scripts /opt/docker-solr/scripts
COPY --chown=solr:solr user /var/solr/data/user
RUN mkdir -p /var/solr/move/user
COPY --chown=solr:solr organization /var/solr/data/organization
RUN mkdir -p /var/solr/move/organization
COPY --chown=solr:solr subOrganization /var/solr/data/subOrganization
RUN mkdir -p /var/solr/move/subOrganization
COPY --chown=solr:solr environment /var/solr/data/environment
RUN mkdir -p /var/solr/move/environment
COPY --chown=solr:solr graph /var/solr/data/graph
RUN mkdir -p /var/solr/move/graph
COPY --chown=solr:solr publishGraph /var/solr/data/publishGraph
RUN mkdir -p /var/solr/move/publishGraph
COPY --chown=solr:solr publishRest /var/solr/data/publishRest
RUN mkdir -p /var/solr/move/publishRest
COPY --chown=solr:solr apiKey /var/solr/data/apiKey
RUN mkdir -p /var/solr/move/apiKey
COPY --chown=solr:solr userSetting /var/solr/data/userSetting
RUN mkdir -p /var/solr/move/userSetting
COPY --chown=solr:solr Configuration /var/solr/data/Configuration
RUN mkdir -p /var/solr/move/Configuration
COPY --chown=solr:solr graphVersions /var/solr/data/graphVersions
RUN mkdir -p /var/solr/move/graphVersions
COPY --chown=solr:solr graphDeployments /var/solr/data/graphDeployments
RUN mkdir -p /var/solr/move/graphDeployments
COPY --chown=solr:solr deploymentConfiguration /var/solr/data/deploymentConfiguration
RUN mkdir -p /var/solr/move/deploymentConfiguration
    
    RUN chmod -R 0777 /var/solr/data && \
    chmod -R 0777 /var/solr/move && \
    chmod -R +x /opt/docker-solr/scripts
    
VOLUME /var/solr
EXPOSE 8983
WORKDIR /opt/solr
USER $SOLR_UID

ENTRYPOINT ["docker-entrypoint.sh"]
CMD ["solr-foreground"]
