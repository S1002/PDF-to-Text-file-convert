# PDF-to-Text-file-convert

##Converting PDF file to Text file.

Moving text files to the folders using keywords.

cheking similarity between the files using BERT pretrained model.
import os
import shutil

exts=[]
files= r'C:\Users\zz2840\Documents\ML\Trust_NHSLA\files'
path = r"C:\Users\zz2840\Documents\ML\Trust_NHSLA"
dir_list = os.listdir(path)
for fp in dir_list:
    # Split the extension from the path and normalise it to lowercase.
    ext = os.path.splitext(fp)[-1].lower()
    exts.append(ext)
fold = list(set(exts))
for i in (fold):
    if not os.path.exists(os.path.join(path, i)):
        os.makedirs(os.path.join(path, i))
dirs = os.listdir(files)
for f in dirs:
    ext = os.path.splitext(f)[-1].lower()
    shutil.move(os.path.join(files, f),os.path.join(path, ext))
    print(ext)
