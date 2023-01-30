# CouchbaseLitePyjnius

**Provato con UBUNTU 20 e UBUNTU 18**

**Eseguire i comandi come utente root, cambiare i path all'occorrenza**

**Installazione di conda e della libreria pyjnius. Uso conda perché provvede autonomamente al setup delle principali lib python e del jdk per pyjnius**

wget -P /tmp https://repo.anaconda.com/archive/Anaconda3-2020.02-Linux-x86_64.sh

bash /tmp/Anaconda3-2020.02-Linux-x86_64.sh -b

eval "$(~/anaconda3/bin/conda shell.bash hook)"

conda init

conda install -c "conda-forge/label/cf202003" pyjnius -y

**Installazione delle librerie Couchbase Lite per Java**

wget -P /tmp https://packages.couchbase.com/releases/couchbase-lite-java/3.0.5/couchbase-lite-java-ee-3.0.5.zip

sudo apt-get update

sudo apt-get install unzip

unzip /tmp/couchbase-lite-java-ee-3.0.5.zip -d .

echo 'export LD_LIBRARY_PATH=/root/couchbase-lite-java-ee-3.0.5-1/support/linux/x86_64/libc++:/root/couchbase-lite-java-ee-3.0.5-1/support/linux/x86_64/libicu:$LD_LIBRARY_PATH' >> ~/.bashrc

source ~/.bashrc

**Esecuzione dello script di esempio, che contiene operazioni key/value, setup replicazione con endpoint remoto e query SQL**

wget https://github.com/marcobevilacqua94/CouchbaseLitePyjnius/raw/main/CBLitePyjnius.py

python3 CBLitePyjnius.py
