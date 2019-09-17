# generate_cloud
#Make a word cloud out of the contents of abstracts from Pubmed

```
#!/usr/bin/bash
#perl -MNet::FTP -e \
   # '$ftp = new Net::FTP("ftp.ncbi.nlm.nih.gov", Passive => 1);
    # $ftp->login; $ftp->binary;
     #$ftp->get("/entrez/entrezdirect/edirect.tar.gz");'
  #gunzip -c edirect.tar.gz | tar xf -
 # rm edirect.tar.gz
 #builtin exit
  #export PATH=${PATH}:$HOME/edirect >& /dev/null || setenv PATH "${PATH}:$HOME/edirect"
  #./edirect/setup.sh

#echo "export PATH=\$PATH:\$HOME/edirect" >> $HOME/.bash_profile

if [ -z $1 ]; then
    echo "Help: Please enter your search terms after the script to generate a word cloud";
else
esearch -db pubmed -query "$1 $2 $3" |   efetch -format abstract > pubmed.txt

#pip install wordcloud

wordcloud_cli --text pubmed.txt --imagefile wordcloud.png;
fi
```
