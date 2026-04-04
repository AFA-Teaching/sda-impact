---
title: "Exercice : Logs erreur"
description: "Exemple de logs terminal avec erreurs Python typiques à analyser et résoudre avec l'IA."
---

# 📄 Test : Logs erreur

Last login: Tue Nov 14 09:12:01 on ttys001  
student@laptop-cours:\~/Documents/Projet\_Data$ ls  
data.csv notes.txt script\_analyse.py  
student@laptop-cours:\~/Documents/Projet\_Data$ python3 script\_analyse.py  
File "script\_analyse.py", line 14  
if prix \> 1000  
^  
SyntaxError: expected ':'  
student@laptop-cours:\~/Documents/Projet\_Data$ \# Ah mince oublié les deux points  
student@laptop-cours:\~/Documents/Projet\_Data$ python3 script\_analyse.py  
Traceback (most recent call last):  
File "script\_analyse.py", line 28, in \<module\>  
calculer\_moyenne(donnees)  
File "script\_analyse.py", line 18, in calculer\_moyenne  
total = sum(dones)  
NameError: name 'dones' is not defined. Did you mean: 'donnees'?  
student@laptop-cours:\~/Documents/Projet\_Data$ \# Pfff faute de frappe  
student@laptop-cours:\~/Documents/Projet\_Data$ python3 script\_analyse.py  
Traceback (most recent call last):  
File "script\_analyse.py", line 2, in \<module\>  
import matplotib.pyplot as plt  
ModuleNotFoundError: No module named 'matplotib'  
student@laptop-cours:\~/Documents/Projet\_Data$ pip install matplotib  
ERROR: Could not find a version that satisfies the requirement matplotib (from versions: none)  
ERROR: No matching distribution found for matplotib  
student@laptop-cours:\~/Documents/Projet\_Data$ \# Mais pourquoi ça marche paaaas ???
