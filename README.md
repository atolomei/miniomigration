<h1>Minio Migration</h1>

 * <p>This program migrates a <a href="https://minio.io">Minio Server</a> 
 * to <a href="https://odilon.io">Odilon</a></p>
 * 
 * <p>The client version of the Minio SDK used here is <b>6.0.13</b> (see pom.xml). <br/>
 * The API methods may be different for newer versions of the Minio SDK</p>
 * 
 * <p>Note that some <b>objectName</b> may be valid for Minio but not for Odilon, in those cases 
 * the migration process converts the objectName into a Odilon supported objectName</p>
 * 
 * <p>Minio SDK returns <b>bucketName</b>, <b>objectName</b> and other values but it does not return the file name (like <i>"test.pdf"</i>), 
 * therefore it is not possible to know the file name from Minio SDK. 
 * We use the objectName as a file name.</p>
 * 
 * <p>Logs:
 * <ul>
 * <li><b>stats.log</b> -> summarized info</li>
 * <li><b>bucket-object.log</b> -> list of objectNames that were normalized to be valid for Odilon </li>
 * <li><b>minio-migration.log</b> -> console log</li>
 * </ul>
 * </p>
 * <p>
 * Sample JVM args: 
 * <ul>
 * <li>-Xbootclasspath/a:.\config</li>
 * <li>-Dlog4j.configurationFile=.\config\log4j2.xml</li>
 * <li>-Xms1G</li>
 * <li>-Xmx4G</li>
 * <li>-DLog4jContextSelector=org.apache.logging.log4j.core.async.AsyncLoggerContextSelector</li>
 * <li>-DMinioEndpoint=http://localhost:9000</li>
 * <li>-DMinioAccessKey=minio</li>
 * <li>-DMinioSecretKey=minio</li>
 * <li>-DOdilonEndpoint=http://localhost</li>
 * <li>-DOdilonAccessKey=odilon</li>
 * <li>-DOdilonSecretKey=odilon</li>
 * <li>-DOdilonPort=92345</li>
 * <li>-DforceAll=false</li>
 * </ul>
 * </p>
