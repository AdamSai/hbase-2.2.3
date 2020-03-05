# Setup

I din .bashrc eller .zshrc (Findes i din home folder /home/{username} fil tilføj de følgende linjer. Husk at ændr så de paths passer til dit system. På Mac burde man kunne bruge `/usr/libexec/java_home` for at finde java filen, og på Ubuntu burde den ligge i `/usr/lib/jvm/`:  
```
# HBASE PATH
export HBASE_HOME=/home/adam/hbase-2.2.3
export PATH=$PATH:$HBASE_HOME/bin
export CLASSPATH=$CLASSPATH:/home/adam/hbase-2.3.3/lib/*
#JAVA PATH
export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64/jre
export PATH=$PATH:$JAVA_HOME/BIN
```  
I `/conf/hbase-env.sh` ændr linjen `export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64/jre` så den passer til dit system.  
I `/conf/hbase-site.xml` ændr følgende linjer så de passer til hvor du har downloadet dette repo:  
```xml
<property>

  <name>hbase.rootdir</name>

  <value>file:/home/adam/hbase-2.2.3</value>

</property>

<property>

  <name>hbase.zookeeper.property.dataDir</name>

  <value>/home/adam/hbase-2.2.3/zookeeper</value>

</property>
```  
Derefter `cd` ind i `/bin/` mappen og der burde du kunne skrive `start-hbase.sh` i din terminal. Til sidst burde du kunne skrive `hbase shell` i konsollen for at åbne shell terminalen.
