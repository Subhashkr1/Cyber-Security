# Saving and Converting Metasploit XML Report

To save an XML report from Metasploit and convert it to a more readable format, such as HTML or PDF, follow these steps:

## 1. Generating the XML Report

First, generate the XML report from Metasploit:

1. **Run the Metasploit Framework (msfconsole)**:
   ```bash
   msfconsole
   ```
2. After running your scans or exploiting targets, use the db_export command to export the data in XML format:
   ```bash
   db_export -f xml -a /path/to/save/report.xml
   ```
-f xml specifies the XML format.
-a includes all the available data in the export.
/path/to/save/report.xml is the path where the XML report will be saved.

## 2. Converting XML Report
**Convert XML to HTML**
You can use various tools or scripts to convert XML to HTML. Here are two methods:

Using xsltproc (XSLT Processor):

Install xsltproc (if not already installed):

```bash
sudo apt-get install xsltproc
```
Create an XSLT stylesheet to convert XML to HTML. Save the following example as report.xsl:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
  <xsl:template match="/">
    <html>
      <body>
        <h1>Metasploit Report</h1>
        <table border="1">
          <tr>
            <th>Host</th>
            <th>Port</th>
            <th>Service</th>
            <th>Details</th>
          </tr>
          <xsl:for-each select="report/host">
            <tr>
              <td><xsl:value-of select="address"/></td>
              <td><xsl:value-of select="port"/></td>
              <td><xsl:value-of select="service"/></td>
              <td><xsl:value-of select="details"/></td>
            </tr>
          </xsl:for-each>
        </table>
      </body>
    </html>
  </xsl:template>
</xsl:stylesheet>
```
Convert XML to HTML using xsltproc:

```bash
xsltproc report.xsl /path/to/save/report.xml > /path/to/save/report.html
```