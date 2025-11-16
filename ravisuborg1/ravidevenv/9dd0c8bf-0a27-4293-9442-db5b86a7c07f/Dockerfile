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
COPY --chown=solr:solr userOrg /var/solr/data/userOrg
RUN mkdir -p /var/solr/move/userOrg
COPY --chown=solr:solr invitation /var/solr/data/invitation
RUN mkdir -p /var/solr/move/invitation
COPY --chown=solr:solr environment /var/solr/data/environment
RUN mkdir -p /var/solr/move/environment
COPY --chown=solr:solr project /var/solr/data/project
RUN mkdir -p /var/solr/move/project
COPY --chown=solr:solr version /var/solr/data/version
RUN mkdir -p /var/solr/move/version
COPY --chown=solr:solr configuration /var/solr/data/configuration
RUN mkdir -p /var/solr/move/configuration
COPY --chown=solr:solr deploymentConfiguration /var/solr/data/deploymentConfiguration
RUN mkdir -p /var/solr/move/deploymentConfiguration
COPY --chown=solr:solr deployment /var/solr/data/deployment
RUN mkdir -p /var/solr/move/deployment
COPY --chown=solr:solr publishLog /var/solr/data/publishLog
RUN mkdir -p /var/solr/move/publishLog
COPY --chown=solr:solr apiKey /var/solr/data/apiKey
RUN mkdir -p /var/solr/move/apiKey
COPY --chown=solr:solr userSetting /var/solr/data/userSetting
RUN mkdir -p /var/solr/move/userSetting
COPY --chown=solr:solr chatHistory /var/solr/data/chatHistory
RUN mkdir -p /var/solr/move/chatHistory
COPY --chown=solr:solr earlyAccess /var/solr/data/earlyAccess
RUN mkdir -p /var/solr/move/earlyAccess
    
    RUN chmod -R 0777 /var/solr/data && \
    chmod -R 0777 /var/solr/move && \
    chmod -R +x /opt/docker-solr/scripts
    
VOLUME /var/solr
EXPOSE 8983
WORKDIR /opt/solr
USER $SOLR_UID

ENTRYPOINT ["docker-entrypoint.sh"]
CMD ["solr-foreground"]
