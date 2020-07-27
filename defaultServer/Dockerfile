# Base Image
FROM websphere-liberty:kernel
 
# Copy application artifacts & configuration
RUN mkdir -p /config
RUN mkdir -p /config/dropins
COPY ./apps/JavaHelloWorldApp.war /config/dropins/JavaHelloWorldApp.war
# RUN chown 1001:0 /config/dropins/JavaHelloWorldApp.war
COPY server.xml /config/server.xml
# RUN chown 1001:0 /config/server.xml
COPY runtime-vars.xml /config/runtime-vars.xml
# RUN chown 1001:0 /config/runtime-vars.xml
 
# Install Liberty features
RUN installUtility install --acceptLicense defaultServer
 
# Optional functionality
# ARG SSL=true
# ARG MP_MONITORING=true
 
# Add interim fixes (optional)
# COPY --chown=1001:0  interim-fixes /opt/ibm/fixes/
 
# This script will add the requested XML snippets, grow image to be fit-for-purpose and apply interim fixes
# RUN configure.sh
