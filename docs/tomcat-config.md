
# Tomcat Configuration Notes

1. Install Apache Tomcat 9 or 10.
2. Enable the **Manager** app and create a deployment user in `conf/tomcat-users.xml`:
   ```xml
   <role rolename="manager-script"/>
   <user username="deployer" password="strongpassword" roles="manager-script"/>
   ```
3. Note your Tomcat URL, e.g., `https://tomcat.example.com` and expose `manager` over HTTPS only.
4. In Jenkins, store:
   - `TOMCAT_URL`
   - `TOMCAT_USER`
   - `TOMCAT_PASS`
5. Ensure firewall allows Jenkins → Tomcat egress.
