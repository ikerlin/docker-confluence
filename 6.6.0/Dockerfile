FROM atlassian/confluence-server:6.6.0

RUN set -x \
    && curl -Ls                "https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-5.1.41.tar.gz" | tar -xz --directory "${CONFLUENCE_INSTALL_DIR}/confluence/WEB-INF/lib" --strip-components=1 --no-same-owner "mysql-connector-java-5.1.41/mysql-connector-java-5.1.41-bin.jar"

# hack
COPY "atlassian-extras-decoder-v2-3.2.jar" "${CONFLUENCE_INSTALL_DIR}/confluence/WEB-INF/lib/"
COPY "atlassian-universal-plugin-manager-plugin-2.22.5.jar" "${CONFLUENCE_INSTALL_DIR}/confluence/WEB-INF/atlassian-bundled-plugins/"