# miniProjet

PARTIE 5
#Question 22:
import numpy as np
import matplotlib.pyplot as plt
M=[[[210, 100, 255],[100, 50, 255],[90, 90, 255],[90, 90, 255],[90, 90, 255],[90, 80, 255]],
[[190, 255,89],[ 201, 255,29],[200, 255,100],[100, 255,90],[20, 255,200], [100, 255,80]],
[[255,0, 0],[ 255,0, 0],[255,0, 0],[255,0, 0],[255,0, 0], [255,0, 0]] ]
plt.imshow(M)
plt.axis ("off")
plt.show ()

M[0][1][1]=50
M[1][0][1]=255
M[2][1][0]=25

#Question 23:
"""on sait que chaque pixel est représenté par 3 octets
donc lea quantité de mémoire nécéssaire pour stocker cette image est:
 n*p*3 = 3*6*3 = 54o = 432 bits"""
 
#Question 24:
def  initImageRGB(imageRGB):
      imageRGB = []
      for x in range(0, 3):
             imageRGB.append([])
             for y in range(0,6):
                   imageRGB[x].append([])
                   for z in range(0,3):
                         i=randrange(0,255)
                         imageRGB[x][y].append(i)
      return imageRGB
#Q1: SYMETRIE VERTICALE
import matplotlib.pyplot as plt
import imageio.v2 as imageio #conversion d'une image à une liste
Img = imageio.imread("cttm1.jpg").tolist()
plt.figure()
plt.imshow(Img)
plt.show()
#affichage de l'image originale
def Symetrie(Img):
#*Renvoie une image symétrique de Img par un axe vertical
     n=len(Img)  # nombre de lignes dans Ing
     p = len(Img[0])  # nombre de colonnes dans Ing
     Z =[[0 for j in range(p)] for i in range(n)]  # Z la matrice nulle
     for i in range(n):
            for j in range(p):
                  Z[i][j]=Img[i][p-1-j]
     return Z
k=Symetrie(Img)
plt.figure()
plt.imshow(k)
plt.show() #affichafe d'une image symétrique par rapport à l'axe verticale

#Q2: SYMETRIE HORIZONTALE
def Symetrie2(Img):
#*Renvoie une image symétrique de Img par un axe horizontale
     n=len(Img)  # nombre de lignes dans Ing
     p = len(Img[0])  # nombre de colonnes dans Ing
     Z =[[0 for j in range(p)] for i in range(n)]  # Z la matrice nulle
     for i in range(n):
            for j in range(p):
                  Z[i][j]=Img[n-1-i][j]
     return Z
Img = imageio.imread("pic.jpg").tolist()
F=Symetrie2(Img)
plt.figure()
plt.imshow(F)
plt.show()


#QUESTION 26
from PIL import Image
from numpy import*
def grayscale(imageRGB):
        GrayImg=[[0]*len(Img[0]) for i in range(len(Img))]#initialiser la matrice 2D en 0
for i in range(len(Img)):
    for j in range(len(Img[0])):
        #print("les valeurs max sont:", (M[i][j][2]+M[i][j][0]+M[i][j][1])//3)
         GrayImg[i][j]=(Img[i][j][2]+Img[i][j][0]+Img[i][j][1])//3 #implémenter la mztrice avec la moyenne de chaque pixel
print(GrayImg)
array = array(GrayImg, dtype=uint8)
new_image = Image.fromarray(array) #convertir la matrice en image
plt.axis("off")
plt.imshow(new_image, cmap = "gray")
#ouvrir l'image
plt.show()

