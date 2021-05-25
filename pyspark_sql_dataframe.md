```python
!wget https://downloads.apache.org/spark/spark-3.1.1/spark-3.1.1-bin-hadoop2.7.tgz
!tar -xvf spark-3.1.1-bin-hadoop2.7.tgz
import os
os.environ["JAVA_HOME"] = "/usr/lib/jvm/java-11-openjdk-amd64"
os.environ["SPARK_HOME"] = "/content/spark-3.1.1-bin-hadoop2.7"
!pip install findspark
import findspark
findspark.init()
from pyspark.sql import SparkSession
spark = SparkSession.builder.master("local[*]").getOrCreate()
```

    --2021-05-07 13:02:05--  https://downloads.apache.org/spark/spark-3.1.1/spark-3.1.1-bin-hadoop2.7.tgz
    Resolving downloads.apache.org (downloads.apache.org)... 135.181.209.10, 135.181.214.104, 88.99.95.219, ...
    Connecting to downloads.apache.org (downloads.apache.org)|135.181.209.10|:443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 224374704 (214M) [application/x-gzip]
    Saving to: ‘spark-3.1.1-bin-hadoop2.7.tgz’
    
    spark-3.1.1-bin-had 100%[===================>] 213.98M  17.5MB/s    in 14s     
    
    2021-05-07 13:02:19 (15.8 MB/s) - ‘spark-3.1.1-bin-hadoop2.7.tgz’ saved [224374704/224374704]
    
    spark-3.1.1-bin-hadoop2.7/
    spark-3.1.1-bin-hadoop2.7/NOTICE
    spark-3.1.1-bin-hadoop2.7/kubernetes/
    spark-3.1.1-bin-hadoop2.7/kubernetes/tests/
    spark-3.1.1-bin-hadoop2.7/kubernetes/tests/python_executable_check.py
    spark-3.1.1-bin-hadoop2.7/kubernetes/tests/autoscale.py
    spark-3.1.1-bin-hadoop2.7/kubernetes/tests/worker_memory_check.py
    spark-3.1.1-bin-hadoop2.7/kubernetes/tests/py_container_checks.py
    spark-3.1.1-bin-hadoop2.7/kubernetes/tests/decommissioning.py
    spark-3.1.1-bin-hadoop2.7/kubernetes/tests/pyfiles.py
    spark-3.1.1-bin-hadoop2.7/kubernetes/tests/decommissioning_cleanup.py
    spark-3.1.1-bin-hadoop2.7/kubernetes/dockerfiles/
    spark-3.1.1-bin-hadoop2.7/kubernetes/dockerfiles/spark/
    spark-3.1.1-bin-hadoop2.7/kubernetes/dockerfiles/spark/decom.sh
    spark-3.1.1-bin-hadoop2.7/kubernetes/dockerfiles/spark/entrypoint.sh
    spark-3.1.1-bin-hadoop2.7/kubernetes/dockerfiles/spark/bindings/
    spark-3.1.1-bin-hadoop2.7/kubernetes/dockerfiles/spark/bindings/R/
    spark-3.1.1-bin-hadoop2.7/kubernetes/dockerfiles/spark/bindings/R/Dockerfile
    spark-3.1.1-bin-hadoop2.7/kubernetes/dockerfiles/spark/bindings/python/
    spark-3.1.1-bin-hadoop2.7/kubernetes/dockerfiles/spark/bindings/python/Dockerfile
    spark-3.1.1-bin-hadoop2.7/kubernetes/dockerfiles/spark/Dockerfile
    spark-3.1.1-bin-hadoop2.7/jars/
    spark-3.1.1-bin-hadoop2.7/jars/jackson-xc-1.9.13.jar
    spark-3.1.1-bin-hadoop2.7/jars/RoaringBitmap-0.9.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/commons-digester-1.8.jar
    spark-3.1.1-bin-hadoop2.7/jars/api-util-1.0.0-M20.jar
    spark-3.1.1-bin-hadoop2.7/jars/hive-vector-code-gen-2.3.7.jar
    spark-3.1.1-bin-hadoop2.7/jars/derby-10.12.1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/commons-beanutils-1.9.4.jar
    spark-3.1.1-bin-hadoop2.7/jars/okhttp-3.12.12.jar
    spark-3.1.1-bin-hadoop2.7/jars/httpcore-4.4.12.jar
    spark-3.1.1-bin-hadoop2.7/jars/logging-interceptor-3.12.12.jar
    spark-3.1.1-bin-hadoop2.7/jars/hadoop-yarn-api-2.7.4.jar
    spark-3.1.1-bin-hadoop2.7/jars/scala-library-2.12.10.jar
    spark-3.1.1-bin-hadoop2.7/jars/spark-mllib-local_2.12-3.1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/parquet-format-2.4.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/kryo-shaded-4.0.2.jar
    spark-3.1.1-bin-hadoop2.7/jars/xercesImpl-2.12.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/commons-logging-1.1.3.jar
    spark-3.1.1-bin-hadoop2.7/jars/commons-compiler-3.0.16.jar
    spark-3.1.1-bin-hadoop2.7/jars/jdo-api-3.0.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/spire-macros_2.12-0.17.0-M1.jar
    spark-3.1.1-bin-hadoop2.7/jars/json4s-core_2.12-3.7.0-M5.jar
    spark-3.1.1-bin-hadoop2.7/jars/JLargeArrays-1.5.jar
    spark-3.1.1-bin-hadoop2.7/jars/jsp-api-2.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/kubernetes-model-autoscaling-4.12.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/jcl-over-slf4j-1.7.30.jar
    spark-3.1.1-bin-hadoop2.7/jars/json4s-ast_2.12-3.7.0-M5.jar
    spark-3.1.1-bin-hadoop2.7/jars/hive-cli-2.3.7.jar
    spark-3.1.1-bin-hadoop2.7/jars/apacheds-i18n-2.0.0-M15.jar
    spark-3.1.1-bin-hadoop2.7/jars/parquet-common-1.10.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/stax-api-1.0.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/jackson-dataformat-yaml-2.10.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/hive-storage-api-2.7.2.jar
    spark-3.1.1-bin-hadoop2.7/jars/algebra_2.12-2.0.0-M2.jar
    spark-3.1.1-bin-hadoop2.7/jars/hadoop-annotations-2.7.4.jar
    spark-3.1.1-bin-hadoop2.7/jars/guice-servlet-3.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/spire-util_2.12-0.17.0-M1.jar
    spark-3.1.1-bin-hadoop2.7/jars/jakarta.activation-api-1.2.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/jline-2.14.6.jar
    spark-3.1.1-bin-hadoop2.7/jars/breeze_2.12-1.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/metrics-jvm-4.1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/dropwizard-metrics-hadoop-metrics2-reporter-0.1.2.jar
    spark-3.1.1-bin-hadoop2.7/jars/machinist_2.12-0.6.8.jar
    spark-3.1.1-bin-hadoop2.7/jars/scala-compiler-2.12.10.jar
    spark-3.1.1-bin-hadoop2.7/jars/commons-pool-1.5.4.jar
    spark-3.1.1-bin-hadoop2.7/jars/spark-network-shuffle_2.12-3.1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/spark-repl_2.12-3.1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/jta-1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/kubernetes-model-admissionregistration-4.12.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/istack-commons-runtime-3.0.8.jar
    spark-3.1.1-bin-hadoop2.7/jars/metrics-graphite-4.1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/hadoop-hdfs-2.7.4.jar
    spark-3.1.1-bin-hadoop2.7/jars/spark-streaming_2.12-3.1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/spark-launcher_2.12-3.1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/objenesis-2.6.jar
    spark-3.1.1-bin-hadoop2.7/jars/commons-collections-3.2.2.jar
    spark-3.1.1-bin-hadoop2.7/jars/audience-annotations-0.5.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/jpam-1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/jakarta.annotation-api-1.3.5.jar
    spark-3.1.1-bin-hadoop2.7/jars/xmlenc-0.52.jar
    spark-3.1.1-bin-hadoop2.7/jars/api-asn1-api-1.0.0-M20.jar
    spark-3.1.1-bin-hadoop2.7/jars/kubernetes-model-common-4.12.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/kubernetes-model-extensions-4.12.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/py4j-0.10.9.jar
    spark-3.1.1-bin-hadoop2.7/jars/hadoop-mapreduce-client-common-2.7.4.jar
    spark-3.1.1-bin-hadoop2.7/jars/spire-platform_2.12-0.17.0-M1.jar
    spark-3.1.1-bin-hadoop2.7/jars/avro-1.8.2.jar
    spark-3.1.1-bin-hadoop2.7/jars/curator-client-2.7.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/javax.inject-1.jar
    spark-3.1.1-bin-hadoop2.7/jars/kubernetes-model-apiextensions-4.12.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/jersey-media-jaxb-2.30.jar
    spark-3.1.1-bin-hadoop2.7/jars/javax.jdo-3.2.0-m3.jar
    spark-3.1.1-bin-hadoop2.7/jars/hadoop-auth-2.7.4.jar
    spark-3.1.1-bin-hadoop2.7/jars/commons-io-2.4.jar
    spark-3.1.1-bin-hadoop2.7/jars/json4s-jackson_2.12-3.7.0-M5.jar
    spark-3.1.1-bin-hadoop2.7/jars/paranamer-2.8.jar
    spark-3.1.1-bin-hadoop2.7/jars/cats-kernel_2.12-2.0.0-M4.jar
    spark-3.1.1-bin-hadoop2.7/jars/spark-mllib_2.12-3.1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/flatbuffers-java-1.9.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/jersey-server-2.30.jar
    spark-3.1.1-bin-hadoop2.7/jars/stream-2.9.6.jar
    spark-3.1.1-bin-hadoop2.7/jars/datanucleus-api-jdo-4.2.4.jar
    spark-3.1.1-bin-hadoop2.7/jars/gson-2.2.4.jar
    spark-3.1.1-bin-hadoop2.7/jars/spark-hive-thriftserver_2.12-3.1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/xml-apis-1.4.01.jar
    spark-3.1.1-bin-hadoop2.7/jars/apacheds-kerberos-codec-2.0.0-M15.jar
    spark-3.1.1-bin-hadoop2.7/jars/antlr4-runtime-4.8-1.jar
    spark-3.1.1-bin-hadoop2.7/jars/hadoop-mapreduce-client-shuffle-2.7.4.jar
    spark-3.1.1-bin-hadoop2.7/jars/kubernetes-model-policy-4.12.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/hive-jdbc-2.3.7.jar
    spark-3.1.1-bin-hadoop2.7/jars/hive-exec-2.3.7-core.jar
    spark-3.1.1-bin-hadoop2.7/jars/opencsv-2.3.jar
    spark-3.1.1-bin-hadoop2.7/jars/kubernetes-model-certificates-4.12.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/avro-mapred-1.8.2-hadoop2.jar
    spark-3.1.1-bin-hadoop2.7/jars/jsr305-3.0.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/macro-compat_2.12-1.1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/spark-sketch_2.12-3.1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/commons-dbcp-1.4.jar
    spark-3.1.1-bin-hadoop2.7/jars/jersey-container-servlet-core-2.30.jar
    spark-3.1.1-bin-hadoop2.7/jars/okio-1.14.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/hk2-api-2.6.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/parquet-jackson-1.10.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/mesos-1.4.0-shaded-protobuf.jar
    spark-3.1.1-bin-hadoop2.7/jars/orc-mapreduce-1.5.12.jar
    spark-3.1.1-bin-hadoop2.7/jars/chill-java-0.9.5.jar
    spark-3.1.1-bin-hadoop2.7/jars/kubernetes-model-settings-4.12.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/spark-tags_2.12-3.1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/jakarta.servlet-api-4.0.3.jar
    spark-3.1.1-bin-hadoop2.7/jars/spark-unsafe_2.12-3.1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/automaton-1.11-8.jar
    spark-3.1.1-bin-hadoop2.7/jars/commons-lang-2.6.jar
    spark-3.1.1-bin-hadoop2.7/jars/jackson-annotations-2.10.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/hk2-utils-2.6.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/velocity-1.5.jar
    spark-3.1.1-bin-hadoop2.7/jars/htrace-core-3.1.0-incubating.jar
    spark-3.1.1-bin-hadoop2.7/jars/jul-to-slf4j-1.7.30.jar
    spark-3.1.1-bin-hadoop2.7/jars/JTransforms-3.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/jersey-client-2.30.jar
    spark-3.1.1-bin-hadoop2.7/jars/spark-catalyst_2.12-3.1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/httpclient-4.5.6.jar
    spark-3.1.1-bin-hadoop2.7/jars/kubernetes-model-discovery-4.12.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/jetty-sslengine-6.1.26.jar
    spark-3.1.1-bin-hadoop2.7/jars/spire_2.12-0.17.0-M1.jar
    spark-3.1.1-bin-hadoop2.7/jars/jersey-hk2-2.30.jar
    spark-3.1.1-bin-hadoop2.7/jars/spark-sql_2.12-3.1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/commons-math3-3.4.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/xbean-asm7-shaded-4.15.jar
    spark-3.1.1-bin-hadoop2.7/jars/spark-network-common_2.12-3.1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/jakarta.validation-api-2.0.2.jar
    spark-3.1.1-bin-hadoop2.7/jars/parquet-encoding-1.10.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/snappy-java-1.1.8.2.jar
    spark-3.1.1-bin-hadoop2.7/jars/slf4j-log4j12-1.7.30.jar
    spark-3.1.1-bin-hadoop2.7/jars/hadoop-mapreduce-client-app-2.7.4.jar
    spark-3.1.1-bin-hadoop2.7/jars/slf4j-api-1.7.30.jar
    spark-3.1.1-bin-hadoop2.7/jars/hive-shims-0.23-2.3.7.jar
    spark-3.1.1-bin-hadoop2.7/jars/guava-14.0.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/stax-api-1.0-2.jar
    spark-3.1.1-bin-hadoop2.7/jars/spark-kubernetes_2.12-3.1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/zjsonpatch-0.3.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/hive-service-rpc-3.1.2.jar
    spark-3.1.1-bin-hadoop2.7/jars/shapeless_2.12-2.3.3.jar
    spark-3.1.1-bin-hadoop2.7/jars/spark-graphx_2.12-3.1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/oro-2.0.8.jar
    spark-3.1.1-bin-hadoop2.7/jars/arrow-memory-netty-2.0.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/kubernetes-model-scheduling-4.12.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/hadoop-yarn-client-2.7.4.jar
    spark-3.1.1-bin-hadoop2.7/jars/libfb303-0.9.3.jar
    spark-3.1.1-bin-hadoop2.7/jars/core-1.1.2.jar
    spark-3.1.1-bin-hadoop2.7/jars/jersey-container-servlet-2.30.jar
    spark-3.1.1-bin-hadoop2.7/jars/datanucleus-rdbms-4.1.19.jar
    spark-3.1.1-bin-hadoop2.7/jars/super-csv-2.2.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/compress-lzf-1.0.3.jar
    spark-3.1.1-bin-hadoop2.7/jars/jackson-module-paranamer-2.10.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/aopalliance-1.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/osgi-resource-locator-1.0.3.jar
    spark-3.1.1-bin-hadoop2.7/jars/jackson-module-scala_2.12-2.10.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/hive-shims-2.3.7.jar
    spark-3.1.1-bin-hadoop2.7/jars/hadoop-yarn-server-common-2.7.4.jar
    spark-3.1.1-bin-hadoop2.7/jars/json-1.8.jar
    spark-3.1.1-bin-hadoop2.7/jars/antlr-runtime-3.5.2.jar
    spark-3.1.1-bin-hadoop2.7/jars/threeten-extra-1.5.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/orc-shims-1.5.12.jar
    spark-3.1.1-bin-hadoop2.7/jars/jetty-6.1.26.jar
    spark-3.1.1-bin-hadoop2.7/jars/arrow-vector-2.0.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/jackson-module-jaxb-annotations-2.10.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/jersey-common-2.30.jar
    spark-3.1.1-bin-hadoop2.7/jars/aircompressor-0.10.jar
    spark-3.1.1-bin-hadoop2.7/jars/lz4-java-1.7.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/hadoop-client-2.7.4.jar
    spark-3.1.1-bin-hadoop2.7/jars/activation-1.1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/commons-crypto-1.1.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/spark-tags_2.12-3.1.1-tests.jar
    spark-3.1.1-bin-hadoop2.7/jars/libthrift-0.12.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/HikariCP-2.5.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/generex-1.0.2.jar
    spark-3.1.1-bin-hadoop2.7/jars/breeze-macros_2.12-1.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/leveldbjni-all-1.8.jar
    spark-3.1.1-bin-hadoop2.7/jars/jaxb-runtime-2.3.2.jar
    spark-3.1.1-bin-hadoop2.7/jars/json4s-scalap_2.12-3.7.0-M5.jar
    spark-3.1.1-bin-hadoop2.7/jars/kubernetes-model-events-4.12.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/commons-lang3-3.10.jar
    spark-3.1.1-bin-hadoop2.7/jars/jackson-datatype-jsr310-2.11.2.jar
    spark-3.1.1-bin-hadoop2.7/jars/commons-httpclient-3.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/kubernetes-client-4.12.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/spark-hive_2.12-3.1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/shims-0.9.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/jackson-core-asl-1.9.13.jar
    spark-3.1.1-bin-hadoop2.7/jars/scala-xml_2.12-1.2.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/hk2-locator-2.6.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/hadoop-common-2.7.4.jar
    spark-3.1.1-bin-hadoop2.7/jars/orc-core-1.5.12.jar
    spark-3.1.1-bin-hadoop2.7/jars/curator-recipes-2.7.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/jackson-mapper-asl-1.9.13.jar
    spark-3.1.1-bin-hadoop2.7/jars/hive-common-2.3.7.jar
    spark-3.1.1-bin-hadoop2.7/jars/xz-1.5.jar
    spark-3.1.1-bin-hadoop2.7/jars/ST4-4.0.4.jar
    spark-3.1.1-bin-hadoop2.7/jars/hive-shims-scheduler-2.3.7.jar
    spark-3.1.1-bin-hadoop2.7/jars/spark-yarn_2.12-3.1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/kubernetes-model-batch-4.12.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/netty-all-4.1.51.Final.jar
    spark-3.1.1-bin-hadoop2.7/jars/parquet-hadoop-1.10.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/chill_2.12-0.9.5.jar
    spark-3.1.1-bin-hadoop2.7/jars/commons-configuration-1.6.jar
    spark-3.1.1-bin-hadoop2.7/jars/jackson-databind-2.10.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/scala-reflect-2.12.10.jar
    spark-3.1.1-bin-hadoop2.7/jars/joda-time-2.10.5.jar
    spark-3.1.1-bin-hadoop2.7/jars/minlog-1.3.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/jakarta.ws.rs-api-2.1.6.jar
    spark-3.1.1-bin-hadoop2.7/jars/aopalliance-repackaged-2.6.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/commons-compress-1.20.jar
    spark-3.1.1-bin-hadoop2.7/jars/spark-core_2.12-3.1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/bonecp-0.8.0.RELEASE.jar
    spark-3.1.1-bin-hadoop2.7/jars/jodd-core-3.5.2.jar
    spark-3.1.1-bin-hadoop2.7/jars/kubernetes-model-storageclass-4.12.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/hadoop-yarn-server-web-proxy-2.7.4.jar
    spark-3.1.1-bin-hadoop2.7/jars/jackson-core-2.10.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/kubernetes-model-core-4.12.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/protobuf-java-2.5.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/commons-net-3.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/hadoop-mapreduce-client-jobclient-2.7.4.jar
    spark-3.1.1-bin-hadoop2.7/jars/datanucleus-core-4.1.17.jar
    spark-3.1.1-bin-hadoop2.7/jars/jackson-jaxrs-1.9.13.jar
    spark-3.1.1-bin-hadoop2.7/jars/janino-3.0.16.jar
    spark-3.1.1-bin-hadoop2.7/jars/hive-shims-common-2.3.7.jar
    spark-3.1.1-bin-hadoop2.7/jars/javolution-5.5.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/kubernetes-model-rbac-4.12.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/transaction-api-1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/kubernetes-model-metrics-4.12.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/jaxb-api-2.2.2.jar
    spark-3.1.1-bin-hadoop2.7/jars/commons-cli-1.2.jar
    spark-3.1.1-bin-hadoop2.7/jars/jakarta.inject-2.6.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/metrics-jmx-4.1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/zstd-jni-1.4.8-1.jar
    spark-3.1.1-bin-hadoop2.7/jars/jakarta.xml.bind-api-2.3.2.jar
    spark-3.1.1-bin-hadoop2.7/jars/commons-codec-1.10.jar
    spark-3.1.1-bin-hadoop2.7/jars/hadoop-yarn-common-2.7.4.jar
    spark-3.1.1-bin-hadoop2.7/jars/curator-framework-2.7.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/arpack_combined_all-0.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/hive-metastore-2.3.7.jar
    spark-3.1.1-bin-hadoop2.7/jars/hive-beeline-2.3.7.jar
    spark-3.1.1-bin-hadoop2.7/jars/metrics-core-4.1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/hive-llap-common-2.3.7.jar
    spark-3.1.1-bin-hadoop2.7/jars/arrow-format-2.0.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/spark-kvstore_2.12-3.1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/javassist-3.25.0-GA.jar
    spark-3.1.1-bin-hadoop2.7/jars/scala-collection-compat_2.12-2.1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/arrow-memory-core-2.0.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/parquet-column-1.10.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/jetty-util-6.1.26.jar
    spark-3.1.1-bin-hadoop2.7/jars/kubernetes-model-coordination-4.12.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/avro-ipc-1.8.2.jar
    spark-3.1.1-bin-hadoop2.7/jars/guice-3.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/commons-text-1.6.jar
    spark-3.1.1-bin-hadoop2.7/jars/kubernetes-model-apps-4.12.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/metrics-json-4.1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/snakeyaml-1.24.jar
    spark-3.1.1-bin-hadoop2.7/jars/ivy-2.4.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/hadoop-mapreduce-client-core-2.7.4.jar
    spark-3.1.1-bin-hadoop2.7/jars/univocity-parsers-2.9.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/pyrolite-4.30.jar
    spark-3.1.1-bin-hadoop2.7/jars/spark-mesos_2.12-3.1.1.jar
    spark-3.1.1-bin-hadoop2.7/jars/log4j-1.2.17.jar
    spark-3.1.1-bin-hadoop2.7/jars/hive-serde-2.3.7.jar
    spark-3.1.1-bin-hadoop2.7/jars/scala-parser-combinators_2.12-1.1.2.jar
    spark-3.1.1-bin-hadoop2.7/jars/kubernetes-model-networking-4.12.0.jar
    spark-3.1.1-bin-hadoop2.7/jars/zookeeper-3.4.14.jar
    spark-3.1.1-bin-hadoop2.7/data/
    spark-3.1.1-bin-hadoop2.7/data/mllib/
    spark-3.1.1-bin-hadoop2.7/data/mllib/sample_lda_data.txt
    spark-3.1.1-bin-hadoop2.7/data/mllib/sample_libsvm_data.txt
    spark-3.1.1-bin-hadoop2.7/data/mllib/sample_svm_data.txt
    spark-3.1.1-bin-hadoop2.7/data/mllib/sample_multiclass_classification_data.txt
    spark-3.1.1-bin-hadoop2.7/data/mllib/sample_linear_regression_data.txt
    spark-3.1.1-bin-hadoop2.7/data/mllib/sample_lda_libsvm_data.txt
    spark-3.1.1-bin-hadoop2.7/data/mllib/sample_fpgrowth.txt
    spark-3.1.1-bin-hadoop2.7/data/mllib/sample_binary_classification_data.txt
    spark-3.1.1-bin-hadoop2.7/data/mllib/sample_isotonic_regression_libsvm_data.txt
    spark-3.1.1-bin-hadoop2.7/data/mllib/iris_libsvm.txt
    spark-3.1.1-bin-hadoop2.7/data/mllib/sample_movielens_data.txt
    spark-3.1.1-bin-hadoop2.7/data/mllib/als/
    spark-3.1.1-bin-hadoop2.7/data/mllib/als/test.data
    spark-3.1.1-bin-hadoop2.7/data/mllib/als/sample_movielens_ratings.txt
    spark-3.1.1-bin-hadoop2.7/data/mllib/sample_kmeans_data.txt
    spark-3.1.1-bin-hadoop2.7/data/mllib/pic_data.txt
    spark-3.1.1-bin-hadoop2.7/data/mllib/images/
    spark-3.1.1-bin-hadoop2.7/data/mllib/images/origin/
    spark-3.1.1-bin-hadoop2.7/data/mllib/images/origin/kittens/
    spark-3.1.1-bin-hadoop2.7/data/mllib/images/origin/kittens/54893.jpg
    spark-3.1.1-bin-hadoop2.7/data/mllib/images/origin/kittens/not-image.txt
    spark-3.1.1-bin-hadoop2.7/data/mllib/images/origin/kittens/DP802813.jpg
    spark-3.1.1-bin-hadoop2.7/data/mllib/images/origin/kittens/29.5.a_b_EGDP022204.jpg
    spark-3.1.1-bin-hadoop2.7/data/mllib/images/origin/kittens/DP153539.jpg
    spark-3.1.1-bin-hadoop2.7/data/mllib/images/origin/license.txt
    spark-3.1.1-bin-hadoop2.7/data/mllib/images/origin/multi-channel/
    spark-3.1.1-bin-hadoop2.7/data/mllib/images/origin/multi-channel/BGRA.png
    spark-3.1.1-bin-hadoop2.7/data/mllib/images/origin/multi-channel/BGRA_alpha_60.png
    spark-3.1.1-bin-hadoop2.7/data/mllib/images/origin/multi-channel/grayscale.jpg
    spark-3.1.1-bin-hadoop2.7/data/mllib/images/origin/multi-channel/chr30.4.184.jpg
    spark-3.1.1-bin-hadoop2.7/data/mllib/images/partitioned/
    spark-3.1.1-bin-hadoop2.7/data/mllib/images/partitioned/cls=multichannel/
    spark-3.1.1-bin-hadoop2.7/data/mllib/images/partitioned/cls=multichannel/date=2018-01/
    spark-3.1.1-bin-hadoop2.7/data/mllib/images/partitioned/cls=multichannel/date=2018-01/BGRA.png
    spark-3.1.1-bin-hadoop2.7/data/mllib/images/partitioned/cls=multichannel/date=2018-01/BGRA_alpha_60.png
    spark-3.1.1-bin-hadoop2.7/data/mllib/images/partitioned/cls=multichannel/date=2018-02/
    spark-3.1.1-bin-hadoop2.7/data/mllib/images/partitioned/cls=multichannel/date=2018-02/grayscale.jpg
    spark-3.1.1-bin-hadoop2.7/data/mllib/images/partitioned/cls=multichannel/date=2018-02/chr30.4.184.jpg
    spark-3.1.1-bin-hadoop2.7/data/mllib/images/partitioned/cls=kittens/
    spark-3.1.1-bin-hadoop2.7/data/mllib/images/partitioned/cls=kittens/date=2018-01/
    spark-3.1.1-bin-hadoop2.7/data/mllib/images/partitioned/cls=kittens/date=2018-01/not-image.txt
    spark-3.1.1-bin-hadoop2.7/data/mllib/images/partitioned/cls=kittens/date=2018-01/29.5.a_b_EGDP022204.jpg
    spark-3.1.1-bin-hadoop2.7/data/mllib/images/partitioned/cls=kittens/date=2018-02/
    spark-3.1.1-bin-hadoop2.7/data/mllib/images/partitioned/cls=kittens/date=2018-02/54893.jpg
    spark-3.1.1-bin-hadoop2.7/data/mllib/images/partitioned/cls=kittens/date=2018-02/DP802813.jpg
    spark-3.1.1-bin-hadoop2.7/data/mllib/images/partitioned/cls=kittens/date=2018-02/DP153539.jpg
    spark-3.1.1-bin-hadoop2.7/data/mllib/images/license.txt
    spark-3.1.1-bin-hadoop2.7/data/mllib/ridge-data/
    spark-3.1.1-bin-hadoop2.7/data/mllib/ridge-data/lpsa.data
    spark-3.1.1-bin-hadoop2.7/data/mllib/kmeans_data.txt
    spark-3.1.1-bin-hadoop2.7/data/mllib/streaming_kmeans_data_test.txt
    spark-3.1.1-bin-hadoop2.7/data/mllib/pagerank_data.txt
    spark-3.1.1-bin-hadoop2.7/data/mllib/gmm_data.txt
    spark-3.1.1-bin-hadoop2.7/data/graphx/
    spark-3.1.1-bin-hadoop2.7/data/graphx/users.txt
    spark-3.1.1-bin-hadoop2.7/data/graphx/followers.txt
    spark-3.1.1-bin-hadoop2.7/data/streaming/
    spark-3.1.1-bin-hadoop2.7/data/streaming/AFINN-111.txt
    spark-3.1.1-bin-hadoop2.7/R/
    spark-3.1.1-bin-hadoop2.7/R/lib/
    spark-3.1.1-bin-hadoop2.7/R/lib/sparkr.zip
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/tests/
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/tests/testthat/
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/tests/testthat/test_basic.R
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/DESCRIPTION
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/profile/
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/profile/shell.R
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/profile/general.R
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/INDEX
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/Meta/
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/Meta/features.rds
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/Meta/links.rds
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/Meta/nsInfo.rds
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/Meta/package.rds
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/Meta/Rd.rds
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/Meta/hsearch.rds
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/help/
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/help/SparkR.rdb
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/help/aliases.rds
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/help/SparkR.rdx
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/help/AnIndex
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/help/paths.rds
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/R/
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/R/SparkR.rdb
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/R/SparkR.rdx
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/R/SparkR
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/NAMESPACE
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/html/
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/html/00Index.html
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/html/R.css
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/worker/
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/worker/worker.R
    spark-3.1.1-bin-hadoop2.7/R/lib/SparkR/worker/daemon.R
    spark-3.1.1-bin-hadoop2.7/README.md
    spark-3.1.1-bin-hadoop2.7/RELEASE
    spark-3.1.1-bin-hadoop2.7/yarn/
    spark-3.1.1-bin-hadoop2.7/yarn/spark-3.1.1-yarn-shuffle.jar
    spark-3.1.1-bin-hadoop2.7/LICENSE
    spark-3.1.1-bin-hadoop2.7/sbin/
    spark-3.1.1-bin-hadoop2.7/sbin/start-workers.sh
    spark-3.1.1-bin-hadoop2.7/sbin/stop-mesos-shuffle-service.sh
    spark-3.1.1-bin-hadoop2.7/sbin/start-master.sh
    spark-3.1.1-bin-hadoop2.7/sbin/workers.sh
    spark-3.1.1-bin-hadoop2.7/sbin/start-worker.sh
    spark-3.1.1-bin-hadoop2.7/sbin/spark-config.sh
    spark-3.1.1-bin-hadoop2.7/sbin/start-history-server.sh
    spark-3.1.1-bin-hadoop2.7/sbin/start-slaves.sh
    spark-3.1.1-bin-hadoop2.7/sbin/spark-daemon.sh
    spark-3.1.1-bin-hadoop2.7/sbin/stop-worker.sh
    spark-3.1.1-bin-hadoop2.7/sbin/stop-mesos-dispatcher.sh
    spark-3.1.1-bin-hadoop2.7/sbin/decommission-worker.sh
    spark-3.1.1-bin-hadoop2.7/sbin/start-mesos-shuffle-service.sh
    spark-3.1.1-bin-hadoop2.7/sbin/decommission-slave.sh
    spark-3.1.1-bin-hadoop2.7/sbin/slaves.sh
    spark-3.1.1-bin-hadoop2.7/sbin/stop-history-server.sh
    spark-3.1.1-bin-hadoop2.7/sbin/start-thriftserver.sh
    spark-3.1.1-bin-hadoop2.7/sbin/stop-thriftserver.sh
    spark-3.1.1-bin-hadoop2.7/sbin/start-slave.sh
    spark-3.1.1-bin-hadoop2.7/sbin/start-all.sh
    spark-3.1.1-bin-hadoop2.7/sbin/stop-slave.sh
    spark-3.1.1-bin-hadoop2.7/sbin/spark-daemons.sh
    spark-3.1.1-bin-hadoop2.7/sbin/stop-workers.sh
    spark-3.1.1-bin-hadoop2.7/sbin/stop-slaves.sh
    spark-3.1.1-bin-hadoop2.7/sbin/stop-all.sh
    spark-3.1.1-bin-hadoop2.7/sbin/start-mesos-dispatcher.sh
    spark-3.1.1-bin-hadoop2.7/sbin/stop-master.sh
    spark-3.1.1-bin-hadoop2.7/examples/
    spark-3.1.1-bin-hadoop2.7/examples/src/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/r/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/r/ml/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/r/ml/survreg.R
    spark-3.1.1-bin-hadoop2.7/examples/src/main/r/ml/glm.R
    spark-3.1.1-bin-hadoop2.7/examples/src/main/r/ml/prefixSpan.R
    spark-3.1.1-bin-hadoop2.7/examples/src/main/r/ml/lm_with_elastic_net.R
    spark-3.1.1-bin-hadoop2.7/examples/src/main/r/ml/powerIterationClustering.R
    spark-3.1.1-bin-hadoop2.7/examples/src/main/r/ml/lda.R
    spark-3.1.1-bin-hadoop2.7/examples/src/main/r/ml/kstest.R
    spark-3.1.1-bin-hadoop2.7/examples/src/main/r/ml/isoreg.R
    spark-3.1.1-bin-hadoop2.7/examples/src/main/r/ml/ml.R
    spark-3.1.1-bin-hadoop2.7/examples/src/main/r/ml/naiveBayes.R
    spark-3.1.1-bin-hadoop2.7/examples/src/main/r/ml/fmRegressor.R
    spark-3.1.1-bin-hadoop2.7/examples/src/main/r/ml/mlp.R
    spark-3.1.1-bin-hadoop2.7/examples/src/main/r/ml/als.R
    spark-3.1.1-bin-hadoop2.7/examples/src/main/r/ml/kmeans.R
    spark-3.1.1-bin-hadoop2.7/examples/src/main/r/ml/svmLinear.R
    spark-3.1.1-bin-hadoop2.7/examples/src/main/r/ml/fmClassifier.R
    spark-3.1.1-bin-hadoop2.7/examples/src/main/r/ml/logit.R
    spark-3.1.1-bin-hadoop2.7/examples/src/main/r/ml/randomForest.R
    spark-3.1.1-bin-hadoop2.7/examples/src/main/r/ml/gbt.R
    spark-3.1.1-bin-hadoop2.7/examples/src/main/r/ml/decisionTree.R
    spark-3.1.1-bin-hadoop2.7/examples/src/main/r/ml/gaussianMixture.R
    spark-3.1.1-bin-hadoop2.7/examples/src/main/r/ml/bisectingKmeans.R
    spark-3.1.1-bin-hadoop2.7/examples/src/main/r/ml/fpm.R
    spark-3.1.1-bin-hadoop2.7/examples/src/main/r/dataframe.R
    spark-3.1.1-bin-hadoop2.7/examples/src/main/r/RSparkSQLExample.R
    spark-3.1.1-bin-hadoop2.7/examples/src/main/r/data-manipulation.R
    spark-3.1.1-bin-hadoop2.7/examples/src/main/r/streaming/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/r/streaming/structured_network_wordcount.R
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/SparkPageRank.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/SkewedGroupByTest.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/AccumulatorMetricsTest.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/HdfsTest.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/Word2VecExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/DeveloperApiExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/MinHashLSHExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/IndexToStringExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/BisectingKMeansExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/CorrelationExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/MulticlassLogisticRegressionWithElasticNetExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/VectorSizeHintExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/NGramExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/BucketedRandomProjectionLSHExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/BinarizerExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/RandomForestExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/StandardScalerExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/LogisticRegressionExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/FeatureHasherExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/OneVsRestExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/StopWordsRemoverExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/LinearSVCExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/GaussianMixtureExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/MaxAbsScalerExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/VarianceThresholdSelectorExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/GBTExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/IsotonicRegressionExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/ModelSelectionViaCrossValidationExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/EstimatorTransformerParamExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/DecisionTreeRegressionExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/RandomForestRegressorExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/PrefixSpanExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/KMeansExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/ModelSelectionViaTrainValidationSplitExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/LogisticRegressionSummaryExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/MultilayerPerceptronClassifierExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/PCAExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/DCTExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/FPGrowthExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/ElementwiseProductExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/GeneralizedLinearRegressionExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/UnivariateFeatureSelectorExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/CountVectorizerExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/MinMaxScalerExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/ChiSquareTestExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/LogisticRegressionWithElasticNetExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/FMRegressorExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/VectorSlicerExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/LinearRegressionExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/StringIndexerExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/GradientBoostedTreeRegressorExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/ALSExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/DecisionTreeClassificationExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/PolynomialExpansionExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/FMClassifierExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/UnaryTransformerExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/ImputerExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/TokenizerExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/DecisionTreeExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/GradientBoostedTreeClassifierExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/PowerIterationClusteringExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/SQLTransformerExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/SummarizerExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/DataFrameExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/BucketizerExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/TfIdfExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/AFTSurvivalRegressionExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/QuantileDiscretizerExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/OneHotEncoderExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/PipelineExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/InteractionExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/LDAExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/RFormulaExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/VectorIndexerExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/VectorAssemblerExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/NormalizerExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/ChiSqSelectorExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/NaiveBayesExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/RandomForestClassifierExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/LinearRegressionWithElasticNetExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ml/RobustScalerExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/LogQuery.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/SparkRemoteFileTest.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/ExceptionHandlingTest.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/pythonconverters/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/pythonconverters/AvroConverters.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/BroadcastTest.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/SparkHdfsLR.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/Word2VecExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/GradientBoostedTreesRunner.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/RandomRDDGeneration.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/PMMLModelExportExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/BisectingKMeansExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/DecisionTreeRunner.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/MultiLabelMetricsExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/CorrelationsExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/LBFGSExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/TFIDFExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/StandardScalerExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/LogisticRegressionWithLBFGSExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/StreamingTestExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/BinaryClassification.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/DenseKMeans.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/GradientBoostingClassificationExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/RankingMetricsExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/GaussianMixtureExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/MultivariateSummarizer.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/IsotonicRegressionExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/PCAOnSourceVectorExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/Correlations.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/HypothesisTestingExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/DecisionTreeRegressionExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/AssociationRulesExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/StreamingLogisticRegression.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/SVDExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/PrefixSpanExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/KMeansExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/SparseNaiveBayes.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/AbstractParams.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/BinaryClassificationMetricsExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/SampledRDDs.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/FPGrowthExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/ElementwiseProductExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/RecommendationExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/TallSkinnySVD.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/HypothesisTestingKolmogorovSmirnovTestExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/GradientBoostingRegressionExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/StreamingKMeansExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/CosineSimilarity.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/RandomForestRegressionExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/StreamingLinearRegressionExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/StratifiedSamplingExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/DecisionTreeClassificationExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/TallSkinnyPCA.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/RandomForestClassificationExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/SimpleFPGrowth.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/LatentDirichletAllocationExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/KernelDensityEstimationExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/PowerIterationClusteringExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/SVMWithSGDExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/LDAExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/MovieLensALS.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/NormalizerExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/MulticlassMetricsExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/ChiSqSelectorExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/SummaryStatisticsExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/PCAOnRowMatrixExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/mllib/NaiveBayesExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/SparkTC.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/DriverSubmissionTest.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/MultiBroadcastTest.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/SparkLR.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/SparkPi.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/graphx/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/graphx/ConnectedComponentsExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/graphx/LiveJournalPageRank.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/graphx/AggregateMessagesExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/graphx/SSSPExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/graphx/SynthBenchmark.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/graphx/TriangleCountingExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/graphx/PageRankExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/graphx/ComprehensiveExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/graphx/Analytics.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/SparkKMeans.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/streaming/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/streaming/clickstream/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/streaming/clickstream/PageViewGenerator.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/streaming/clickstream/PageViewStream.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/streaming/DirectKafkaWordCount.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/streaming/HdfsWordCount.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/streaming/DirectKerberizedKafkaWordCount.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/streaming/RecoverableNetworkWordCount.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/streaming/NetworkWordCount.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/streaming/QueueStream.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/streaming/SqlNetworkWordCount.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/streaming/CustomReceiver.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/streaming/RawNetworkGrep.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/streaming/StatefulNetworkWordCount.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/streaming/StreamingExamples.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/LocalLR.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/LocalKMeans.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/GroupByTest.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/LocalALS.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/sql/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/sql/SimpleTypedAggregator.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/sql/UserDefinedUntypedAggregation.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/sql/hive/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/sql/hive/SparkHiveExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/sql/RDDRelation.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/sql/SparkSQLExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/sql/SQLDataSourceExample.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/sql/streaming/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/sql/streaming/StructuredKerberizedKafkaWordCount.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/sql/streaming/StructuredNetworkWordCount.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/sql/streaming/StructuredNetworkWordCountWindowed.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/sql/streaming/StructuredKafkaWordCount.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/sql/streaming/StructuredSessionization.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/sql/UserDefinedTypedAggregation.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/sql/UserDefinedScalar.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/SimpleSkewedGroupByTest.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/LocalFileLR.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/LocalPi.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/DFSReadWriteTest.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scala/org/apache/spark/examples/SparkALS.scala
    spark-3.1.1-bin-hadoop2.7/examples/src/main/resources/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/resources/people.json
    spark-3.1.1-bin-hadoop2.7/examples/src/main/resources/users.avro
    spark-3.1.1-bin-hadoop2.7/examples/src/main/resources/people.csv
    spark-3.1.1-bin-hadoop2.7/examples/src/main/resources/users.parquet
    spark-3.1.1-bin-hadoop2.7/examples/src/main/resources/users.orc
    spark-3.1.1-bin-hadoop2.7/examples/src/main/resources/dir1/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/resources/dir1/file1.parquet
    spark-3.1.1-bin-hadoop2.7/examples/src/main/resources/dir1/dir2/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/resources/dir1/dir2/file2.parquet
    spark-3.1.1-bin-hadoop2.7/examples/src/main/resources/dir1/file3.json
    spark-3.1.1-bin-hadoop2.7/examples/src/main/resources/user.avsc
    spark-3.1.1-bin-hadoop2.7/examples/src/main/resources/full_user.avsc
    spark-3.1.1-bin-hadoop2.7/examples/src/main/resources/kv1.txt
    spark-3.1.1-bin-hadoop2.7/examples/src/main/resources/people.txt
    spark-3.1.1-bin-hadoop2.7/examples/src/main/resources/employees.json
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaStringIndexerExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaChiSqSelectorExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaLabeledDocument.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaLogisticRegressionWithElasticNetExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaPolynomialExpansionExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaTfIdfExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaBucketizerExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaLogisticRegressionSummaryExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaSummarizerExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaQuantileDiscretizerExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaBinarizerExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaOneHotEncoderExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaStandardScalerExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaDCTExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaDecisionTreeRegressionExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaRandomForestClassifierExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaOneVsRestExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaGeneralizedLinearRegressionExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaGaussianMixtureExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaWord2VecExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaNormalizerExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaLDAExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaCountVectorizerExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaMultilayerPerceptronClassifierExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaMinMaxScalerExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaCorrelationExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaNGramExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaImputerExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaMinHashLSHExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaVectorSizeHintExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaFMClassifierExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaFeatureHasherExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaModelSelectionViaTrainValidationSplitExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaSQLTransformerExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaKMeansExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaVectorAssemblerExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaGradientBoostedTreeRegressorExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaPrefixSpanExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaFMRegressorExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaNaiveBayesExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaMulticlassLogisticRegressionWithElasticNetExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaModelSelectionViaCrossValidationExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaDocument.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaUnivariateFeatureSelectorExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaGradientBoostedTreeClassifierExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaRandomForestRegressorExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaAFTSurvivalRegressionExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaIsotonicRegressionExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaElementwiseProductExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaALSExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaBucketedRandomProjectionLSHExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaVarianceThresholdSelectorExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaVectorSlicerExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaTokenizerExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaRFormulaExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaEstimatorTransformerParamExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaPowerIterationClusteringExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaBisectingKMeansExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaMaxAbsScalerExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaDecisionTreeClassificationExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaPCAExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaPipelineExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaStopWordsRemoverExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaIndexToStringExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaFPGrowthExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaVectorIndexerExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaInteractionExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaChiSquareTestExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaRobustScalerExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaLinearRegressionWithElasticNetExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/ml/JavaLinearSVCExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/JavaWordCount.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/JavaHdfsLR.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/JavaStatusTrackerDemo.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaChiSqSelectorExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaHypothesisTestingKolmogorovSmirnovTestExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaRandomForestRegressionExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaSimpleFPGrowth.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaRandomForestClassificationExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaMulticlassClassificationMetricsExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaKernelDensityEstimationExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaSummaryStatisticsExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaDecisionTreeRegressionExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaGradientBoostingClassificationExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaGaussianMixtureExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaStratifiedSamplingExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaSVDExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaAssociationRulesExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaALS.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaKMeansExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaSVMWithSGDExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaPrefixSpanExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaNaiveBayesExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaLogisticRegressionWithLBFGSExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaLBFGSExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaGradientBoostingRegressionExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaRankingMetricsExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaIsotonicRegressionExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaElementwiseProductExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaCorrelationsExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaPowerIterationClusteringExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaBisectingKMeansExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaDecisionTreeClassificationExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaPCAExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaRecommendationExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaLatentDirichletAllocationExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaHypothesisTestingExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaMultiLabelClassificationMetricsExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaBinaryClassificationMetricsExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/mllib/JavaStreamingTestExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/JavaPageRank.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/JavaLogQuery.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/streaming/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/streaming/JavaStatefulNetworkWordCount.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/streaming/JavaCustomReceiver.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/streaming/JavaRecord.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/streaming/JavaNetworkWordCount.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/streaming/JavaDirectKerberizedKafkaWordCount.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/streaming/JavaDirectKafkaWordCount.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/streaming/JavaSqlNetworkWordCount.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/streaming/JavaRecoverableNetworkWordCount.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/streaming/JavaQueueStream.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/JavaSparkPi.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/sql/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/sql/JavaUserDefinedScalar.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/sql/hive/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/sql/hive/JavaSparkHiveExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/sql/JavaUserDefinedTypedAggregation.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/sql/JavaSQLDataSourceExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/sql/JavaSparkSQLExample.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/sql/JavaUserDefinedUntypedAggregation.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/sql/streaming/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/sql/streaming/JavaStructuredKafkaWordCount.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/sql/streaming/JavaStructuredNetworkWordCountWindowed.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/sql/streaming/JavaStructuredSessionization.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/sql/streaming/JavaStructuredNetworkWordCount.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/sql/streaming/JavaStructuredKerberizedKafkaWordCount.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/java/org/apache/spark/examples/JavaTC.java
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scripts/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/scripts/getGpusResources.sh
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/kmeans.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/dct_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/count_vectorizer_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/chisq_selector_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/gradient_boosted_tree_regressor_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/tf_idf_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/cross_validator.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/linear_regression_with_elastic_net.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/normalizer_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/fm_regressor_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/univariate_feature_selector_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/polynomial_expansion_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/pipeline_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/generalized_linear_regression_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/multilayer_perceptron_classification.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/bisecting_k_means_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/chi_square_test_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/train_validation_split.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/stopwords_remover_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/linearsvc.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/lda_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/random_forest_regressor_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/vector_assembler_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/word2vec_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/string_indexer_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/decision_tree_classification_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/index_to_string_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/bucketizer_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/vector_size_hint_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/vector_indexer_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/tokenizer_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/robust_scaler_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/standard_scaler_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/kmeans_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/power_iteration_clustering_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/naive_bayes_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/pca_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/aft_survival_regression.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/min_max_scaler_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/elementwise_product_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/dataframe_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/n_gram_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/rformula_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/one_vs_rest_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/als_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/onehot_encoder_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/vector_slicer_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/logistic_regression_with_elastic_net.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/sql_transformer.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/multiclass_logistic_regression_with_elastic_net.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/summarizer_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/quantile_discretizer_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/feature_hasher_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/imputer_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/bucketed_random_projection_lsh_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/estimator_transformer_param_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/gradient_boosted_tree_classifier_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/logistic_regression_summary_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/decision_tree_regression_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/fm_classifier_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/gaussian_mixture_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/fpgrowth_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/variance_threshold_selector_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/random_forest_classifier_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/correlation_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/min_hash_lsh_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/binarizer_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/prefixspan_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/max_abs_scaler_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/isotonic_regression_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/ml/interaction_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/logistic_regression.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/als.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/word2vec.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/correlations_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/gradient_boosting_classification_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/kernel_density_estimation_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/hypothesis_testing_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/svd_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/kmeans.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/latent_dirichlet_allocation_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/tf_idf_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/correlations.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/random_forest_regression_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/normalizer_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/logistic_regression.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/multi_label_metrics_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/gradient_boosting_regression_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/random_forest_classification_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/streaming_linear_regression_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/sampled_rdds.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/bisecting_k_means_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/logistic_regression_with_lbfgs_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/k_means_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/streaming_k_means_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/word2vec_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/multi_class_metrics_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/decision_tree_classification_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/summary_statistics_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/binary_classification_metrics_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/standard_scaler_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/power_iteration_clustering_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/gaussian_mixture_model.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/regression_metrics_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/naive_bayes_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/elementwise_product_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/linear_regression_with_sgd_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/pca_rowmatrix_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/hypothesis_testing_kolmogorov_smirnov_test_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/random_rdd_generation.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/decision_tree_regression_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/gaussian_mixture_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/recommendation_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/fpgrowth_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/ranking_metrics_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/svm_with_sgd_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/isotonic_regression_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/mllib/stratified_sampling_example.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/wordcount.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/status_api_demo.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/pagerank.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/sort.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/transitive_closure.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/avro_inputformat.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/pi.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/streaming/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/streaming/queue_stream.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/streaming/stateful_network_wordcount.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/streaming/network_wordjoinsentiments.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/streaming/sql_network_wordcount.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/streaming/network_wordcount.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/streaming/hdfs_wordcount.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/streaming/recoverable_network_wordcount.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/sql/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/sql/datasource.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/sql/hive.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/sql/arrow.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/sql/streaming/
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/sql/streaming/structured_network_wordcount_windowed.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/sql/streaming/structured_network_wordcount.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/sql/streaming/structured_kafka_wordcount.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/sql/basic.py
    spark-3.1.1-bin-hadoop2.7/examples/src/main/python/parquet_inputformat.py
    spark-3.1.1-bin-hadoop2.7/examples/jars/
    spark-3.1.1-bin-hadoop2.7/examples/jars/spark-examples_2.12-3.1.1.jar
    spark-3.1.1-bin-hadoop2.7/examples/jars/scopt_2.12-3.7.1.jar
    spark-3.1.1-bin-hadoop2.7/conf/
    spark-3.1.1-bin-hadoop2.7/conf/metrics.properties.template
    spark-3.1.1-bin-hadoop2.7/conf/workers.template
    spark-3.1.1-bin-hadoop2.7/conf/fairscheduler.xml.template
    spark-3.1.1-bin-hadoop2.7/conf/log4j.properties.template
    spark-3.1.1-bin-hadoop2.7/conf/spark-defaults.conf.template
    spark-3.1.1-bin-hadoop2.7/conf/spark-env.sh.template
    spark-3.1.1-bin-hadoop2.7/bin/
    spark-3.1.1-bin-hadoop2.7/bin/sparkR.cmd
    spark-3.1.1-bin-hadoop2.7/bin/sparkR
    spark-3.1.1-bin-hadoop2.7/bin/spark-submit
    spark-3.1.1-bin-hadoop2.7/bin/pyspark2.cmd
    spark-3.1.1-bin-hadoop2.7/bin/spark-class
    spark-3.1.1-bin-hadoop2.7/bin/pyspark.cmd
    spark-3.1.1-bin-hadoop2.7/bin/spark-submit2.cmd
    spark-3.1.1-bin-hadoop2.7/bin/load-spark-env.cmd
    spark-3.1.1-bin-hadoop2.7/bin/spark-sql
    spark-3.1.1-bin-hadoop2.7/bin/docker-image-tool.sh
    spark-3.1.1-bin-hadoop2.7/bin/find-spark-home.cmd
    spark-3.1.1-bin-hadoop2.7/bin/load-spark-env.sh
    spark-3.1.1-bin-hadoop2.7/bin/pyspark
    spark-3.1.1-bin-hadoop2.7/bin/spark-shell.cmd
    spark-3.1.1-bin-hadoop2.7/bin/spark-shell2.cmd
    spark-3.1.1-bin-hadoop2.7/bin/spark-submit.cmd
    spark-3.1.1-bin-hadoop2.7/bin/beeline.cmd
    spark-3.1.1-bin-hadoop2.7/bin/find-spark-home
    spark-3.1.1-bin-hadoop2.7/bin/spark-class.cmd
    spark-3.1.1-bin-hadoop2.7/bin/sparkR2.cmd
    spark-3.1.1-bin-hadoop2.7/bin/beeline
    spark-3.1.1-bin-hadoop2.7/bin/spark-class2.cmd
    spark-3.1.1-bin-hadoop2.7/bin/spark-sql.cmd
    spark-3.1.1-bin-hadoop2.7/bin/run-example
    spark-3.1.1-bin-hadoop2.7/bin/spark-shell
    spark-3.1.1-bin-hadoop2.7/bin/run-example.cmd
    spark-3.1.1-bin-hadoop2.7/bin/spark-sql2.cmd
    spark-3.1.1-bin-hadoop2.7/python/
    spark-3.1.1-bin-hadoop2.7/python/.gitignore
    spark-3.1.1-bin-hadoop2.7/python/run-tests-with-coverage
    spark-3.1.1-bin-hadoop2.7/python/mypy.ini
    spark-3.1.1-bin-hadoop2.7/python/pylintrc
    spark-3.1.1-bin-hadoop2.7/python/MANIFEST.in
    spark-3.1.1-bin-hadoop2.7/python/README.md
    spark-3.1.1-bin-hadoop2.7/python/test_coverage/
    spark-3.1.1-bin-hadoop2.7/python/test_coverage/coverage_daemon.py
    spark-3.1.1-bin-hadoop2.7/python/test_coverage/conf/
    spark-3.1.1-bin-hadoop2.7/python/test_coverage/conf/spark-defaults.conf
    spark-3.1.1-bin-hadoop2.7/python/test_coverage/sitecustomize.py
    spark-3.1.1-bin-hadoop2.7/python/run-tests.py
    spark-3.1.1-bin-hadoop2.7/python/setup.py
    spark-3.1.1-bin-hadoop2.7/python/test_support/
    spark-3.1.1-bin-hadoop2.7/python/test_support/userlibrary.py
    spark-3.1.1-bin-hadoop2.7/python/test_support/hello/
    spark-3.1.1-bin-hadoop2.7/python/test_support/hello/sub_hello/
    spark-3.1.1-bin-hadoop2.7/python/test_support/hello/sub_hello/sub_hello.txt
    spark-3.1.1-bin-hadoop2.7/python/test_support/hello/hello.txt
    spark-3.1.1-bin-hadoop2.7/python/test_support/userlib-0.1.zip
    spark-3.1.1-bin-hadoop2.7/python/test_support/SimpleHTTPServer.py
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/people.json
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/people_array.json
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/people_array_utf16le.json
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/text-test.txt
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/ages.csv
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/parquet_partitioned/
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/parquet_partitioned/year=2015/
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/parquet_partitioned/year=2015/month=10/
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/parquet_partitioned/year=2015/month=10/day=26/
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/parquet_partitioned/year=2015/month=10/day=26/.part-r-00005.gz.parquet.crc
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/parquet_partitioned/year=2015/month=10/day=26/part-r-00005.gz.parquet
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/parquet_partitioned/year=2015/month=10/day=25/
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/parquet_partitioned/year=2015/month=10/day=25/.part-r-00002.gz.parquet.crc
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/parquet_partitioned/year=2015/month=10/day=25/.part-r-00004.gz.parquet.crc
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/parquet_partitioned/year=2015/month=10/day=25/part-r-00004.gz.parquet
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/parquet_partitioned/year=2015/month=10/day=25/part-r-00002.gz.parquet
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/parquet_partitioned/year=2015/month=9/
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/parquet_partitioned/year=2015/month=9/day=1/
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/parquet_partitioned/year=2015/month=9/day=1/.part-r-00007.gz.parquet.crc
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/parquet_partitioned/year=2015/month=9/day=1/part-r-00007.gz.parquet
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/parquet_partitioned/_metadata
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/parquet_partitioned/year=2014/
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/parquet_partitioned/year=2014/month=9/
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/parquet_partitioned/year=2014/month=9/day=1/
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/parquet_partitioned/year=2014/month=9/day=1/.part-r-00008.gz.parquet.crc
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/parquet_partitioned/year=2014/month=9/day=1/part-r-00008.gz.parquet
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/parquet_partitioned/_common_metadata
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/parquet_partitioned/_SUCCESS
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/orc_partitioned/
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/orc_partitioned/b=1/
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/orc_partitioned/b=1/c=1/
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/orc_partitioned/b=1/c=1/part-r-00000-829af031-b970-49d6-ad39-30460a0be2c8.orc
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/orc_partitioned/b=1/c=1/.part-r-00000-829af031-b970-49d6-ad39-30460a0be2c8.orc.crc
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/orc_partitioned/b=0/
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/orc_partitioned/b=0/c=0/
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/orc_partitioned/b=0/c=0/part-r-00000-829af031-b970-49d6-ad39-30460a0be2c8.orc
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/orc_partitioned/b=0/c=0/.part-r-00000-829af031-b970-49d6-ad39-30460a0be2c8.orc.crc
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/orc_partitioned/_SUCCESS
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/ages_newlines.csv
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/streaming/
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/streaming/text-test.txt
    spark-3.1.1-bin-hadoop2.7/python/test_support/sql/people1.json
    spark-3.1.1-bin-hadoop2.7/python/pyspark/
    spark-3.1.1-bin-hadoop2.7/python/pyspark/tests/
    spark-3.1.1-bin-hadoop2.7/python/pyspark/tests/test_rddbarrier.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/tests/test_worker.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/tests/test_serializers.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/tests/test_util.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/tests/test_rdd.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/tests/__init__.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/tests/test_broadcast.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/tests/test_appsubmit.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/tests/test_profiler.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/tests/test_pin_thread.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/tests/test_install_spark.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/tests/test_shuffle.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/tests/test_join.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/tests/test_taskcontext.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/tests/test_context.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/tests/test_readwrite.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/tests/test_conf.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/tests/test_daemon.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/__init__.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/_typing.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/testing/
    spark-3.1.1-bin-hadoop2.7/python/pyspark/testing/mlutils.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/testing/__init__.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/testing/mllibutils.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/testing/utils.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/testing/sqlutils.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/testing/streamingutils.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/accumulators.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/rddsampler.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/install.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/status.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/tests/
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/tests/test_algorithms.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/tests/test_evaluation.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/tests/test_util.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/tests/test_feature.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/tests/test_pipeline.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/tests/test_wrapper.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/tests/__init__.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/tests/test_tuning.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/tests/test_persistence.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/tests/test_param.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/tests/test_training_summary.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/tests/test_linalg.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/tests/test_image.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/tests/test_stat.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/tests/test_base.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/evaluation.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/_typing.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/functions.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/recommendation.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/tuning.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/fpm.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/pipeline.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/base.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/feature.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/wrapper.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/__init__.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/stat.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/stat.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/image.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/classification.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/common.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/pipeline.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/recommendation.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/clustering.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/regression.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/param/
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/param/__init__.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/param/_shared_params_code_gen.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/param/__init__.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/param/shared.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/param/_shared_params_code_gen.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/param/shared.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/feature.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/classification.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/tree.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/util.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/tuning.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/fpm.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/regression.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/functions.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/base.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/wrapper.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/image.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/tree.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/clustering.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/common.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/linalg/
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/linalg/__init__.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/linalg/__init__.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/evaluation.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/ml/util.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/context.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/find_spark_home.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/serializers.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/java_gateway.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/traceback_utils.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/resource/
    spark-3.1.1-bin-hadoop2.7/python/pyspark/resource/tests/
    spark-3.1.1-bin-hadoop2.7/python/pyspark/resource/tests/__init__.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/resource/tests/test_resources.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/resource/profile.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/resource/__init__.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/resource/information.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/resource/requests.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/resource/information.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/resource/requests.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/resource/profile.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/conf.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/resultiterable.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/version.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/__init__.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/files.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/tests/
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/tests/test_algorithms.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/tests/test_streaming_algorithms.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/tests/test_util.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/tests/test_feature.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/tests/__init__.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/tests/test_linalg.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/tests/test_stat.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/evaluation.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/_typing.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/recommendation.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/fpm.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/feature.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/__init__.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/classification.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/common.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/random.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/recommendation.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/clustering.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/regression.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/feature.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/classification.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/tree.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/util.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/fpm.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/regression.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/random.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/stat/
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/stat/__init__.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/stat/distribution.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/stat/__init__.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/stat/KernelDensity.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/stat/_statistics.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/stat/distribution.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/stat/test.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/stat/test.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/stat/_statistics.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/stat/KernelDensity.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/tree.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/clustering.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/common.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/linalg/
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/linalg/__init__.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/linalg/__init__.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/linalg/distributed.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/linalg/distributed.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/evaluation.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/mllib/util.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/resultiterable.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/profiler.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/statcounter.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/join.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/daemon.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/rdd.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/context.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/cloudpickle/
    spark-3.1.1-bin-hadoop2.7/python/pyspark/cloudpickle/cloudpickle_fast.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/cloudpickle/__init__.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/cloudpickle/compat.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/cloudpickle/cloudpickle.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/storagelevel.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/version.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/py.typed
    spark-3.1.1-bin-hadoop2.7/python/pyspark/files.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/worker.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/statcounter.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/conf.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/shell.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/streaming/
    spark-3.1.1-bin-hadoop2.7/python/pyspark/streaming/tests/
    spark-3.1.1-bin-hadoop2.7/python/pyspark/streaming/tests/test_listener.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/streaming/tests/test_kinesis.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/streaming/tests/__init__.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/streaming/tests/test_dstream.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/streaming/tests/test_context.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/streaming/dstream.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/streaming/kinesis.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/streaming/context.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/streaming/dstream.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/streaming/listener.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/streaming/__init__.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/streaming/kinesis.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/streaming/listener.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/streaming/context.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/streaming/util.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/accumulators.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/profiler.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/status.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/broadcast.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/tests/
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/tests/test_functions.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/tests/test_readwriter.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/tests/test_utils.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/tests/test_pandas_grouped_map.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/tests/test_dataframe.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/tests/test_pandas_map.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/tests/test_udf.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/tests/test_streaming.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/tests/__init__.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/tests/test_serde.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/tests/test_pandas_udf_window.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/tests/test_group.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/tests/test_pandas_udf.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/tests/test_pandas_cogrouped_map.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/tests/test_pandas_udf_grouped_agg.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/tests/test_pandas_udf_scalar.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/tests/test_catalog.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/tests/test_datasources.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/tests/test_pandas_udf_typehints.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/tests/test_types.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/tests/test_column.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/tests/test_context.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/tests/test_conf.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/tests/test_arrow.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/tests/test_session.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/__init__.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/pandas/
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/pandas/map_ops.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/pandas/functions.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/pandas/serializers.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/pandas/__init__.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/pandas/typehints.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/pandas/group_ops.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/pandas/map_ops.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/pandas/types.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/pandas/conversion.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/pandas/group_ops.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/pandas/functions.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/pandas/utils.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/pandas/conversion.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/pandas/_typing/
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/pandas/_typing/__init__.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/pandas/_typing/protocols/
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/pandas/_typing/protocols/__init__.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/pandas/_typing/protocols/series.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/pandas/_typing/protocols/frame.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/_typing.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/functions.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/readwriter.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/streaming.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/context.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/column.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/catalog.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/types.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/window.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/udf.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/conf.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/__init__.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/session.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/column.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/group.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/catalog.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/group.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/context.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/dataframe.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/types.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/functions.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/conf.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/udf.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/dataframe.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/avro/
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/avro/functions.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/avro/__init__.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/avro/functions.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/utils.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/readwriter.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/window.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/session.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/sql/streaming.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/shuffle.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/rdd.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/taskcontext.pyi
    spark-3.1.1-bin-hadoop2.7/python/pyspark/taskcontext.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/_globals.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/broadcast.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/util.py
    spark-3.1.1-bin-hadoop2.7/python/pyspark/storagelevel.py
    spark-3.1.1-bin-hadoop2.7/python/.coveragerc
    spark-3.1.1-bin-hadoop2.7/python/docs/
    spark-3.1.1-bin-hadoop2.7/python/docs/make2.bat
    spark-3.1.1-bin-hadoop2.7/python/docs/source/
    spark-3.1.1-bin-hadoop2.7/python/docs/source/reference/
    spark-3.1.1-bin-hadoop2.7/python/docs/source/reference/pyspark.ss.rst
    spark-3.1.1-bin-hadoop2.7/python/docs/source/reference/index.rst
    spark-3.1.1-bin-hadoop2.7/python/docs/source/reference/pyspark.ml.rst
    spark-3.1.1-bin-hadoop2.7/python/docs/source/reference/pyspark.rst
    spark-3.1.1-bin-hadoop2.7/python/docs/source/reference/pyspark.mllib.rst
    spark-3.1.1-bin-hadoop2.7/python/docs/source/reference/pyspark.streaming.rst
    spark-3.1.1-bin-hadoop2.7/python/docs/source/reference/pyspark.sql.rst
    spark-3.1.1-bin-hadoop2.7/python/docs/source/reference/pyspark.resource.rst
    spark-3.1.1-bin-hadoop2.7/python/docs/source/index.rst
    spark-3.1.1-bin-hadoop2.7/python/docs/source/getting_started/
    spark-3.1.1-bin-hadoop2.7/python/docs/source/getting_started/index.rst
    spark-3.1.1-bin-hadoop2.7/python/docs/source/getting_started/quickstart.ipynb
    spark-3.1.1-bin-hadoop2.7/python/docs/source/getting_started/install.rst
    spark-3.1.1-bin-hadoop2.7/python/docs/source/conf.py
    spark-3.1.1-bin-hadoop2.7/python/docs/source/_templates/
    spark-3.1.1-bin-hadoop2.7/python/docs/source/_templates/autosummary/
    spark-3.1.1-bin-hadoop2.7/python/docs/source/_templates/autosummary/class.rst
    spark-3.1.1-bin-hadoop2.7/python/docs/source/_templates/autosummary/class_with_docs.rst
    spark-3.1.1-bin-hadoop2.7/python/docs/source/_static/
    spark-3.1.1-bin-hadoop2.7/python/docs/source/_static/copybutton.js
    spark-3.1.1-bin-hadoop2.7/python/docs/source/_static/css/
    spark-3.1.1-bin-hadoop2.7/python/docs/source/_static/css/pyspark.css
    spark-3.1.1-bin-hadoop2.7/python/docs/source/development/
    spark-3.1.1-bin-hadoop2.7/python/docs/source/development/setting_ide.rst
    spark-3.1.1-bin-hadoop2.7/python/docs/source/development/index.rst
    spark-3.1.1-bin-hadoop2.7/python/docs/source/development/debugging.rst
    spark-3.1.1-bin-hadoop2.7/python/docs/source/development/testing.rst
    spark-3.1.1-bin-hadoop2.7/python/docs/source/development/contributing.rst
    spark-3.1.1-bin-hadoop2.7/python/docs/source/user_guide/
    spark-3.1.1-bin-hadoop2.7/python/docs/source/user_guide/arrow_pandas.rst
    spark-3.1.1-bin-hadoop2.7/python/docs/source/user_guide/index.rst
    spark-3.1.1-bin-hadoop2.7/python/docs/source/user_guide/python_packaging.rst
    spark-3.1.1-bin-hadoop2.7/python/docs/source/migration_guide/
    spark-3.1.1-bin-hadoop2.7/python/docs/source/migration_guide/pyspark_2.3.0_to_2.3.1_above.rst
    spark-3.1.1-bin-hadoop2.7/python/docs/source/migration_guide/index.rst
    spark-3.1.1-bin-hadoop2.7/python/docs/source/migration_guide/pyspark_2.4_to_3.0.rst
    spark-3.1.1-bin-hadoop2.7/python/docs/source/migration_guide/pyspark_1.0_1.2_to_1.3.rst
    spark-3.1.1-bin-hadoop2.7/python/docs/source/migration_guide/pyspark_2.3_to_2.4.rst
    spark-3.1.1-bin-hadoop2.7/python/docs/source/migration_guide/pyspark_1.4_to_1.5.rst
    spark-3.1.1-bin-hadoop2.7/python/docs/source/migration_guide/pyspark_2.2_to_2.3.rst
    spark-3.1.1-bin-hadoop2.7/python/docs/make.bat
    spark-3.1.1-bin-hadoop2.7/python/docs/Makefile
    spark-3.1.1-bin-hadoop2.7/python/lib/
    spark-3.1.1-bin-hadoop2.7/python/lib/PY4J_LICENSE.txt
    spark-3.1.1-bin-hadoop2.7/python/lib/py4j-0.10.9-src.zip
    spark-3.1.1-bin-hadoop2.7/python/lib/pyspark.zip
    spark-3.1.1-bin-hadoop2.7/python/run-tests
    spark-3.1.1-bin-hadoop2.7/python/setup.cfg
    spark-3.1.1-bin-hadoop2.7/licenses/
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-respond.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-sbt-launch-lib.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-antlr.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-dagre-d3.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-pyrolite.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-sorttable.js.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-janino.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-protobuf.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-jquery.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-scopt.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-netlib.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-d3.min.js.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-graphlib-dot.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-AnchorJS.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-datatables.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-pmml-model.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-paranamer.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-jakarta-ws-rs-api
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-dnsjava.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-jakarta.xml.bind-api.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-jakarta-annotation-api
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-CC0.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-jodd.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-f2j.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-machinist.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-javolution.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-modernizr.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-spire.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-leveldbjni.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-join.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-zstd-jni.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-slf4j.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-arpack.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-jsp-api.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-JTransforms.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-JLargeArrays.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-bootstrap.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-reflectasm.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-javassist.html
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-zstd.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-json-formatter.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-matchMedia-polyfill.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-scala.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-jakarta.activation-api.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-automaton.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-javax-transaction-transaction-api.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-jaxb-runtime.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-minlog.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-mustache.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-xmlenc.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-jline.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-istack-commons-runtime.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-py4j.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-vis-timeline.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-re2j.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-kryo.txt
    spark-3.1.1-bin-hadoop2.7/licenses/LICENSE-cloudpickle.txt
    Collecting findspark
      Downloading https://files.pythonhosted.org/packages/fc/2d/2e39f9a023479ea798eed4351cd66f163ce61e00c717e03c37109f00c0f2/findspark-1.4.2-py2.py3-none-any.whl
    Installing collected packages: findspark
    Successfully installed findspark-1.4.2
    


```python
!wget https://raw.githubusercontent.com/futurexskill/bidata/master/retailstore.csv
```

    --2021-05-07 13:03:05--  https://raw.githubusercontent.com/futurexskill/bidata/master/retailstore.csv
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 185.199.108.133, 185.199.109.133, 185.199.110.133, ...
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)|185.199.108.133|:443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 279 [text/plain]
    Saving to: ‘retailstore.csv’
    
    retailstore.csv     100%[===================>]     279  --.-KB/s    in 0s      
    
    2021-05-07 13:03:05 (12.3 MB/s) - ‘retailstore.csv’ saved [279/279]
    
    


```python
!ls
```

    retailstore.csv  spark-3.1.1-bin-hadoop2.7
    sample_data	 spark-3.1.1-bin-hadoop2.7.tgz
    


```python
customer_df = spark.read.csv("retailstore.csv",header=True)
```


```python
type(customer_df)
```




    pyspark.sql.dataframe.DataFrame




```python
customer_df.show()
```

    +----+------+------+-------+---------+
    | Age|Salary|Gender|Country|Purchased|
    +----+------+------+-------+---------+
    |  18| 20000|  Male|Germany|        N|
    |  19| 22000|Female| France|        N|
    |  20| 24000|Female|England|        N|
    |  21|  null|  Male|England|        N|
    |  22| 50000|  Male| France|        Y|
    |  23| 35000|Female|England|        N|
    |  24|  null|  Male|Germany|        N|
    |  25| 32000|Female| France|        Y|
    |null| 35000|  Male|Germany|        N|
    |  27| 37000|Female| France|        N|
    +----+------+------+-------+---------+
    
    


```python
customer_df.show(3)
```

    +---+------+------+-------+---------+
    |Age|Salary|Gender|Country|Purchased|
    +---+------+------+-------+---------+
    | 18| 20000|  Male|Germany|        N|
    | 19| 22000|Female| France|        N|
    | 20| 24000|Female|England|        N|
    +---+------+------+-------+---------+
    only showing top 3 rows
    
    


```python
customer_df.describe().show()
```

    +-------+-----------------+-----------------+------+-------+---------+
    |summary|              Age|           Salary|Gender|Country|Purchased|
    +-------+-----------------+-----------------+------+-------+---------+
    |  count|                9|                8|    10|     10|       10|
    |   mean|22.11111111111111|          31875.0|  null|   null|     null|
    | stddev|2.934469476943168|9818.895777311942|  null|   null|     null|
    |    min|               18|            20000|Female|England|        N|
    |    max|               27|            50000|  Male|Germany|        Y|
    +-------+-----------------+-----------------+------+-------+---------+
    
    


```python
country_df = customer_df.select("country")
```


```python
type(country_df)
```




    pyspark.sql.dataframe.DataFrame




```python
country_df.show()
```

    +-------+
    |country|
    +-------+
    |Germany|
    | France|
    |England|
    |England|
    | France|
    |England|
    |Germany|
    | France|
    |Germany|
    | France|
    +-------+
    
    


```python
customer_df.groupBy("country").count().show()
```

    +-------+-----+
    |country|count|
    +-------+-----+
    |Germany|    3|
    | France|    4|
    |England|    3|
    +-------+-----+
    
    


```python
customer_df.groupBy("gender").count().show()
```

    +------+-----+
    |gender|count|
    +------+-----+
    |Female|    5|
    |  Male|    5|
    +------+-----+
    
    


```python
customer_df.createOrReplaceTempView("customer")

```


```python
results = spark.sql("select * from customer")

```


```python
type(results)
```




    pyspark.sql.dataframe.DataFrame




```python
new_results = spark.sql("select * from customer where age>22")

```


```python
new_results.show()
```

    +---+------+------+-------+---------+
    |Age|Salary|Gender|Country|Purchased|
    +---+------+------+-------+---------+
    | 23| 35000|Female|England|        N|
    | 24|  null|  Male|Germany|        N|
    | 25| 32000|Female| France|        Y|
    | 27| 37000|Female| France|        N|
    +---+------+------+-------+---------+
    
    


```python
filtered_df = customer_df.filter('age>22')
```


```python
filtered_df.show()
```

    +---+------+------+-------+---------+
    |Age|Salary|Gender|Country|Purchased|
    +---+------+------+-------+---------+
    | 23| 35000|Female|England|        N|
    | 24|  null|  Male|Germany|        N|
    | 25| 32000|Female| France|        Y|
    | 27| 37000|Female| France|        N|
    +---+------+------+-------+---------+
    
    


```python
customer_df.groupBy("gender").agg({"salary": "avg", "age": "max"}).show()
```

    +------+-----------+--------+
    |gender|avg(salary)|max(age)|
    +------+-----------+--------+
    |Female|    30000.0|      27|
    |  Male|    35000.0|      24|
    +------+-----------+--------+
    
    


```python
customer_df.select(["age","salary"]).show()
```

    +----+------+
    | age|salary|
    +----+------+
    |  18| 20000|
    |  19| 22000|
    |  20| 24000|
    |  21|  null|
    |  22| 50000|
    |  23| 35000|
    |  24|  null|
    |  25| 32000|
    |null| 35000|
    |  27| 37000|
    +----+------+
    
    


```python
customer_df.withColumn('doublesalary',customer_df['salary']*2).show()
```

    +----+------+------+-------+---------+------------+
    | Age|Salary|Gender|Country|Purchased|doublesalary|
    +----+------+------+-------+---------+------------+
    |  18| 20000|  Male|Germany|        N|     40000.0|
    |  19| 22000|Female| France|        N|     44000.0|
    |  20| 24000|Female|England|        N|     48000.0|
    |  21|  null|  Male|England|        N|        null|
    |  22| 50000|  Male| France|        Y|    100000.0|
    |  23| 35000|Female|England|        N|     70000.0|
    |  24|  null|  Male|Germany|        N|        null|
    |  25| 32000|Female| France|        Y|     64000.0|
    |null| 35000|  Male|Germany|        N|     70000.0|
    |  27| 37000|Female| France|        N|     74000.0|
    +----+------+------+-------+---------+------------+
    
    


```python
customer_df.show()
```

    +----+------+------+-------+---------+
    | Age|Salary|Gender|Country|Purchased|
    +----+------+------+-------+---------+
    |  18| 20000|  Male|Germany|        N|
    |  19| 22000|Female| France|        N|
    |  20| 24000|Female|England|        N|
    |  21|  null|  Male|England|        N|
    |  22| 50000|  Male| France|        Y|
    |  23| 35000|Female|England|        N|
    |  24|  null|  Male|Germany|        N|
    |  25| 32000|Female| France|        Y|
    |null| 35000|  Male|Germany|        N|
    |  27| 37000|Female| France|        N|
    +----+------+------+-------+---------+
    
    


```python
new_customer_df = customer_df.withColumn('doublesalary',customer_df['salary']*2)
```


```python
new_customer_df.show()
```

    +----+------+------+-------+---------+------------+
    | Age|Salary|Gender|Country|Purchased|doublesalary|
    +----+------+------+-------+---------+------------+
    |  18| 20000|  Male|Germany|        N|     40000.0|
    |  19| 22000|Female| France|        N|     44000.0|
    |  20| 24000|Female|England|        N|     48000.0|
    |  21|  null|  Male|England|        N|        null|
    |  22| 50000|  Male| France|        Y|    100000.0|
    |  23| 35000|Female|England|        N|     70000.0|
    |  24|  null|  Male|Germany|        N|        null|
    |  25| 32000|Female| France|        Y|     64000.0|
    |null| 35000|  Male|Germany|        N|     70000.0|
    |  27| 37000|Female| France|        N|     74000.0|
    +----+------+------+-------+---------+------------+
    
    


```python
from pyspark.sql.functions import lit
customer_df.withColumn("new_col",lit("A")).show()
```

    +----+------+------+-------+---------+-------+
    | Age|Salary|Gender|Country|Purchased|new_col|
    +----+------+------+-------+---------+-------+
    |  18| 20000|  Male|Germany|        N|      A|
    |  19| 22000|Female| France|        N|      A|
    |  20| 24000|Female|England|        N|      A|
    |  21|  null|  Male|England|        N|      A|
    |  22| 50000|  Male| France|        Y|      A|
    |  23| 35000|Female|England|        N|      A|
    |  24|  null|  Male|Germany|        N|      A|
    |  25| 32000|Female| France|        Y|      A|
    |null| 35000|  Male|Germany|        N|      A|
    |  27| 37000|Female| France|        N|      A|
    +----+------+------+-------+---------+-------+
    
    


```python
customer_df.withColumnRenamed('salary', 'income').show()
```

    +----+------+------+-------+---------+
    | Age|income|Gender|Country|Purchased|
    +----+------+------+-------+---------+
    |  18| 20000|  Male|Germany|        N|
    |  19| 22000|Female| France|        N|
    |  20| 24000|Female|England|        N|
    |  21|  null|  Male|England|        N|
    |  22| 50000|  Male| France|        Y|
    |  23| 35000|Female|England|        N|
    |  24|  null|  Male|Germany|        N|
    |  25| 32000|Female| France|        Y|
    |null| 35000|  Male|Germany|        N|
    |  27| 37000|Female| France|        N|
    +----+------+------+-------+---------+
    
    


```python
customer_df.filter("salary > 30000").select('age').show()
```

    +----+
    | age|
    +----+
    |  22|
    |  23|
    |  25|
    |null|
    |  27|
    +----+
    
    


```python
spark.sql("select age from customer where salary > 30000").show()
```

    +----+
    | age|
    +----+
    |  22|
    |  23|
    |  25|
    |null|
    |  27|
    +----+
    
    


```python
customer_df.filter("salary > 30000").select('age','country').show()
```

    +----+-------+
    | age|country|
    +----+-------+
    |  22| France|
    |  23|England|
    |  25| France|
    |null|Germany|
    |  27| France|
    +----+-------+
    
    


```python
spark.sql("select age,country from customer where salary > 30000").show()
```

    +----+-------+
    | age|country|
    +----+-------+
    |  22| France|
    |  23|England|
    |  25| France|
    |null|Germany|
    |  27| France|
    +----+-------+
    
    


```python
customer_df.filter("salary > 30000 and salary < 40000 ").select('age','country').show()
```

    +----+-------+
    | age|country|
    +----+-------+
    |  23|England|
    |  25| France|
    |null|Germany|
    |  27| France|
    +----+-------+
    
    


```python
spark.sql("select age,country from customer where salary > 30000 and salary < 40000").show()
```

    +----+-------+
    | age|country|
    +----+-------+
    |  23|England|
    |  25| France|
    |null|Germany|
    |  27| France|
    +----+-------+
    
    


```python
from pyspark.sql.functions import countDistinct, avg,stddev
```


```python
customer_df.select(countDistinct("country")).show()

```

    +-----------------------+
    |count(DISTINCT country)|
    +-----------------------+
    |                      3|
    +-----------------------+
    
    


```python
customer_df.select(countDistinct("country").alias("Distinct Countries")).show()
```

    +------------------+
    |Distinct Countries|
    +------------------+
    |                 3|
    +------------------+
    
    


```python
customer_df.select(avg('salary')).show()
```

    +-----------+
    |avg(salary)|
    +-----------+
    |    31875.0|
    +-----------+
    
    


```python
customer_df.select(avg('age')).show()
```

    +-----------------+
    |         avg(age)|
    +-----------------+
    |22.11111111111111|
    +-----------------+
    
    


```python
customer_df.select(stddev("salary")).show()
#Standard deviation
```

    +-------------------+
    |stddev_samp(salary)|
    +-------------------+
    |  9818.895777311942|
    +-------------------+
    
    


```python
customer_df.select(stddev("age")).show()
```

    +-----------------+
    | stddev_samp(age)|
    +-----------------+
    |2.934469476943168|
    +-----------------+
    
    


```python
from pyspark.sql.functions import format_number
```


```python
salary_std = customer_df.select(stddev("salary").alias('std'))

```


```python
salary_std.show()

```

    +-----------------+
    |              std|
    +-----------------+
    |9818.895777311942|
    +-----------------+
    
    


```python
salary_std.select(format_number('std',2)).show()

```

    +---------------------+
    |format_number(std, 2)|
    +---------------------+
    |             9,818.90|
    +---------------------+
    
    


```python
customer_df.orderBy("salary").show()  #sort the data 

```

    +----+------+------+-------+---------+
    | Age|Salary|Gender|Country|Purchased|
    +----+------+------+-------+---------+
    |  21|  null|  Male|England|        N|
    |  24|  null|  Male|Germany|        N|
    |  18| 20000|  Male|Germany|        N|
    |  19| 22000|Female| France|        N|
    |  20| 24000|Female|England|        N|
    |  25| 32000|Female| France|        Y|
    |null| 35000|  Male|Germany|        N|
    |  23| 35000|Female|England|        N|
    |  27| 37000|Female| France|        N|
    |  22| 50000|  Male| France|        Y|
    +----+------+------+-------+---------+
    
    


```python
from pyspark.sql.functions import col
customer_df.orderBy(col("salary").desc()).show()

```

    +----+------+------+-------+---------+
    | Age|Salary|Gender|Country|Purchased|
    +----+------+------+-------+---------+
    |  22| 50000|  Male| France|        Y|
    |  27| 37000|Female| France|        N|
    |  23| 35000|Female|England|        N|
    |null| 35000|  Male|Germany|        N|
    |  25| 32000|Female| France|        Y|
    |  20| 24000|Female|England|        N|
    |  19| 22000|Female| France|        N|
    |  18| 20000|  Male|Germany|        N|
    |  21|  null|  Male|England|        N|
    |  24|  null|  Male|Germany|        N|
    +----+------+------+-------+---------+
    
    


```python
from pyspark.sql.functions import col
customer_df.orderBy(col("salary").asc()).show()
```

    +----+------+------+-------+---------+
    | Age|Salary|Gender|Country|Purchased|
    +----+------+------+-------+---------+
    |  21|  null|  Male|England|        N|
    |  24|  null|  Male|Germany|        N|
    |  18| 20000|  Male|Germany|        N|
    |  19| 22000|Female| France|        N|
    |  20| 24000|Female|England|        N|
    |  25| 32000|Female| France|        Y|
    |null| 35000|  Male|Germany|        N|
    |  23| 35000|Female|England|        N|
    |  27| 37000|Female| France|        N|
    |  22| 50000|  Male| France|        Y|
    +----+------+------+-------+---------+
    
    


```python
new_df = customer_df.drop("purchased")
```


```python
new_df.show()
```

    +----+------+------+-------+
    | Age|Salary|Gender|Country|
    +----+------+------+-------+
    |  18| 20000|  Male|Germany|
    |  19| 22000|Female| France|
    |  20| 24000|Female|England|
    |  21|  null|  Male|England|
    |  22| 50000|  Male| France|
    |  23| 35000|Female|England|
    |  24|  null|  Male|Germany|
    |  25| 32000|Female| France|
    |null| 35000|  Male|Germany|
    |  27| 37000|Female| France|
    +----+------+------+-------+
    
    


```python
customer_df.na.drop().show()   #drop all the row in which is having the null value in any of the column

```

    +---+------+------+-------+---------+
    |Age|Salary|Gender|Country|Purchased|
    +---+------+------+-------+---------+
    | 18| 20000|  Male|Germany|        N|
    | 19| 22000|Female| France|        N|
    | 20| 24000|Female|England|        N|
    | 22| 50000|  Male| France|        Y|
    | 23| 35000|Female|England|        N|
    | 25| 32000|Female| France|        Y|
    | 27| 37000|Female| France|        N|
    +---+------+------+-------+---------+
    
    


```python
customer_df.na.fill('NEW VALUE').show()    # Repalce all the value in the new value

```

    +---------+---------+------+-------+---------+
    |      Age|   Salary|Gender|Country|Purchased|
    +---------+---------+------+-------+---------+
    |       18|    20000|  Male|Germany|        N|
    |       19|    22000|Female| France|        N|
    |       20|    24000|Female|England|        N|
    |       21|NEW VALUE|  Male|England|        N|
    |       22|    50000|  Male| France|        Y|
    |       23|    35000|Female|England|        N|
    |       24|NEW VALUE|  Male|Germany|        N|
    |       25|    32000|Female| France|        Y|
    |NEW VALUE|    35000|  Male|Germany|        N|
    |       27|    37000|Female| France|        N|
    +---------+---------+------+-------+---------+
    
    


```python

```
