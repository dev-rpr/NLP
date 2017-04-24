import docx2txt
import tkinter as tk
import tkinter, tkinter.constants, tkinter.filedialog
import re
def removearticles(text):
    articles = {'a': '', 'an':'', 'and':'', 'the':'','his': '','her': '','this': '' \
                , 'all':'', 'its':'', 'one':'', 'now':'', 'also':'', 'had':'' \
                , 'him':'', 'to':'', 'only':'', 'has':'', 'they':'', 'are':'' \
                , 'our':'', 'be':'', 'we':'', 'by':'', 'of':'', 'other':'' \
                , 'into':'', 'from':''}
    rest = []
    temp = []    
    for i in text.split(','):
        temp.append(i)
    text = ' '.join(temp)
    temp = []    
    for i in text.split('.'):
        temp.append(i)
    text = ' '.join(temp)

    for word in text.split():
        if word not in articles:
            rest.append(word)
    #return ' '.join(rest)            
    return ' '.join(e for e in rest if e.isalpha())
  
def unique_file(input_filename, output_filename):
    input_file = open(input_filename, 'r')
    file_contents = docx2txt.process(input_filename).lower().encode("ascii", "ignore")
    input_file.close()

    file1 = open("D:\\word_org.txt", 'w')
    file1.write(str(file_contents) + "\n")
    file1.close()
    
    file_contents = removearticles(file_contents)
    word_list = file_contents.split()    

    file = open(output_filename, 'w')
    unique_words = set(word_list)
    for word in unique_words:
        file.write(str(word) + "\n")
    file.close()
    
root = tk.Tk()
root.withdraw()
filename = tkinter.filedialog.askopenfilename(initialdir = "/",title = "Select file",filetypes = (("word files","*.doc"),("word files","*.docx")))
input_filename = filename
output_filename = "D:\\Word_res.txt"
unique_file(input_filename, output_filename)
print ('done')    
