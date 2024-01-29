<h1>Minio to Odilon Migration</h1>

  <p>This program migrates a <a href="https://minio.io">Minio Server</a> 
  to <a href="https://odilon.io">Odilon</a></p>

  <p>It is a multithreaded gateway that iterates reading a buffer of items from Minio and sending them in parallel to Odilon.</p>

  <p>The client version of the Minio SDK used here is <b>6.0.13</b> (see 
    <a href="https://github.com/atolomei/miniomigration/blob/main/pom.xml">pom.xml</a>). <br/>
  The API methods may be different for newer versions of the Minio SDK</p>
  
  <p>Note that some <b>objectName</b> may be valid for Minio but not for Odilon, in those cases 
  the migration process converts the objectName into a Odilon supported objectName. The list of objectNames converted is <b>./logs/bucket-object.log</p></b>.</p>
  
  <p>Minio SDK returns <b>bucketName</b>, <b>objectName</b> and other values but it does not return the file name (like <i>"test.pdf"</i>), 
  therefore it is not possible to know the file name from Minio SDK. 
  We use the objectName as a file name.</p>
  
  <p>Logs:
  <ul>
  <li><b>stats.log</b> -> summarized info</li>
  <li><b>bucket-object.log</b> -> list of objectNames that were normalized to be valid for Odilon </li>
  <li><b>minio-migration.log</b> -> console log</li>
  </ul>
  </p>
  <p>
  Sample JVM args: 
  <ul>
  <li>-Xbootclasspath/a:.\config</li>
  <li>-Dlog4j.configurationFile=.\config\log4j2.xml</li>
  <li>-Xms1G</li>
  <li>-Xmx4G</li>
  <li>-DLog4jContextSelector=org.apache.logging.log4j.core.async.AsyncLoggerContextSelector</li>
  <li>-DMinioEndpoint=http://localhost:9000</li>
  <li>-DMinioAccessKey=minio</li>
  <li>-DMinioSecretKey=minio</li>
  <li>-DOdilonEndpoint=http://localhost</li>
  <li>-DOdilonAccessKey=odilon</li>
  <li>-DOdilonSecretKey=odilon</li>
  <li>-DOdilonPort=92345</li>
  <li>-DforceAll=false</li>
  </ul>
  </p>

<h2>Download</h2>
<p>
<ul>
<li><a href="https://odilon.io#download" target="_blank">Odilon Server</a></li>	
<li><a href="https://odilon.io#download" target="_blank">Odilon Java SDK</a></li>	
</ul>
</p>

<h2>Resources</h2>
<p>
<ul>
<li><a href="https://odilon.io" target="_blank">Odilon website</a></li>	
<li><a href="https://odilon.io/configuration-linux.html" target="_blank">Installation, Configuration and Operation on Linux</a></li>	
<li><a href="https://odilon.io/configuration-windows.html" target="_blank">Installation, Configuration and Operation on Windows</a></li>		
<li><a href="https://odilon.io/development.html" target="_blank">Java Application Development with Odilon</a></li>	
<li><a href="https://odilon.io/javadoc/index.html" target="_blank">Odilon SDK Javadoc</a></li>	
<li><a href="https://twitter.com/odilonSoftware" target="_blank">Twitter</a></li>
</ul>
</p>

<h2>SDK Source Code</h2>
<p>
<ul>
<li class="list-item"><a href="https://github.com/atolomei/odilon-client" target="_blank">odilon-client</a></li>
<li class="list-item"><a href="https://github.com/atolomei/odilon-model" target="_blank">odilon-model</a></li>
</ul>
</p>

