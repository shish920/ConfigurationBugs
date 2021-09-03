## gedit 
 ubuntu 16.04 gedit汉字乱码解决  
 type `gsettings set org.gnome.gedit.preferences.encodings candidate-encodings "['GB18030', 'GB2312', 'GBK', 'UTF-8', 'BIG5', 'CURRENT', 'UTF-16']"`
 
## conda environment transfer
1. conda env export > env_filename.yaml
2. pip freeze > requirements.txt
3. conda env create -f env_filename.yaml
4. cat requirements.txt | xargs -n 1 pip install
5. then install the error packages separately.

