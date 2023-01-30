# CouchbaseLitePyjnius

**Provato con UBUNTU 22, UBUNTU 20 e UBUNTU 18 da immagine nuova**

**Installazione di conda e della libreria pyjnius. Uso conda perché provvede autonomamente al setup delle principali lib python e del jdk per pyjnius**

**Eseguire i comandi dalla propria home**

cd ~

wget -P /tmp https://repo.anaconda.com/archive/Anaconda3-2020.02-Linux-x86_64.sh

bash /tmp/Anaconda3-2020.02-Linux-x86_64.sh -b

eval "$(~/anaconda3/bin/conda shell.bash hook)"

conda init

conda install -c "conda-forge/label/cf202003" pyjnius -y

**Installazione delle librerie Couchbase Lite per Java**

wget -P /tmp https://packages.couchbase.com/releases/couchbase-lite-java/3.0.5/couchbase-lite-java-ee-3.0.5.zip

apt-get download unzip

dpkg -x unzip* unzip

unzip/usr/bin/unzip /tmp/couchbase-lite-java-ee-3.0.5.zip -d .

echo 'export LD_LIBRARY_PATH=\~/couchbase-lite-java-ee-3.0.5-1/support/linux/x86_64/libc++:\~/couchbase-lite-java-ee-3.0.5-1/support/linux/x86_64/libicu:$LD_LIBRARY_PATH' >> \~/.bashrc

source ~/.bashrc

**Esecuzione dello script di esempio, che contiene operazioni key/value, setup replicazione con endpoint remoto e query SQL**

wget https://github.com/marcobevilacqua94/CouchbaseLitePyjnius/raw/main/CBLitePyjnius.py

python3 CBLitePyjnius.py
