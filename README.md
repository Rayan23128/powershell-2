PS C:\temp> Set-Location -Path C:\
#Une écriture possible pour la création d'un dossier
New-Item -ItemType Directory -Path C:\ -Name FolderTest1
#Une autre écriture possible pour la création d'un dossier
New-Item -ItemType Directory -Path C:\FolderTest2
#Création de fichier vide dans le dossier c:\FolderTest
New-Item -ItemType File -Path C:\FolderTest1 -Name File1
New-Item -ItemType File -Path C:\FolderTest1 -Name File2
New-Item -ItemType File -Path C:\FolderTest1 -Name File3
New-Item -ItemType File -Path C:\FolderTest1 -Name File4
New-Item -ItemType File -Path C:\FolderTest1 -Name File5
#Création de fichier vide dans le dossier c:\FolderTest2
$Count = 6
Do
{
    New-Item -ItemType File -Path C:\FolderTest2 -Name "File$Count"
    $Count++
}
While ($Count -lt 11)


    Répertoire : C:\


Mode                 LastWriteTime         Length Name                                                                                               
----                 -------------         ------ ----                                                                                               
d-----        20/09/2022     17:31                FolderTest1                                                                                        
d-----        20/09/2022     17:31                FolderTest2                                                                                        


    Répertoire : C:\FolderTest1


Mode                 LastWriteTime         Length Name                                                                                               
----                 -------------         ------ ----                                                                                               
-a----        20/09/2022     17:31              0 File1                                                                                              
-a----        20/09/2022     17:31              0 File2                                                                                              
-a----        20/09/2022     17:31              0 File3                                                                                              
-a----        20/09/2022     17:31              0 File4                                                                                              
-a----        20/09/2022     17:31              0 File5                                                                                              


    Répertoire : C:\FolderTest2


Mode                 LastWriteTime         Length Name                                                                                               
----                 -------------         ------ ----                                                                                               
-a----        20/09/2022     17:31              0 File6                                                                                              
-a----        20/09/2022     17:31              0 File7                                                                                              
-a----        20/09/2022     17:31              0 File8                                                                                              
-a----        20/09/2022     17:31              0 File9                                                                                              
-a----        20/09/2022     17:31              0 File10                                                                                             



PS C:\> Get-ChildItem C:\FolderTest2


    Répertoire : C:\FolderTest2


Mode                 LastWriteTime         Length Name                                                                                               
----                 -------------         ------ ----                                                                                               
-a----        20/09/2022     17:31              0 File10                                                                                             
-a----        20/09/2022     17:31              0 File6                                                                                              
-a----        20/09/2022     17:31              0 File7                                                                                              
-a----        20/09/2022     17:31              0 File8                                                                                              
-a----        20/09/2022     17:31              0 File9                                                                                              



PS C:\> New-Item c:\EvenFolder
New-Item : L'accès au chemin d'accès 'C:\EvenFolder' est refusé.
Au caractère Ligne:1 : 1
+ New-Item c:\EvenFolder
+ ~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : PermissionDenied: (C:\EvenFolder:String) [New-Item], UnauthorizedAccessException
    + FullyQualifiedErrorId : NewItemUnauthorizedAccessError,Microsoft.PowerShell.Commands.NewItemCommand
 

PS C:\> sudo  New-Item c:\EvenFolder
sudo : Le terme «sudo» n'est pas reconnu comme nom d'applet de commande, fonction, fichier de script ou programme exécutable. Vérifiez l'orthographe 
du nom, ou si un chemin d'accès existe, vérifiez que le chemin d'accès est correct et réessayez.
Au caractère Ligne:1 : 1
+ sudo  New-Item c:\EvenFolder
+ ~~~~
    + CategoryInfo          : ObjectNotFound: (sudo:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException
 

PS C:\> New-Item -ItemType Directory -Path C:\FolderTest1
New-Item : Il existe déjà un élément avec le nom spécifié C:\FolderTest1.
Au caractère Ligne:1 : 1
+ New-Item -ItemType Directory -Path C:\FolderTest1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ResourceExists: (C:\FolderTest1:String) [New-Item], IOException
    + FullyQualifiedErrorId : DirectoryExist,Microsoft.PowerShell.Commands.NewItemCommand
 

PS C:\> New-Item -ItemType Directory -Path c:\EvenFolder


    Répertoire : C:\


Mode                 LastWriteTime         Length Name                                                                                               
----                 -------------         ------ ----                                                                                               
d-----        20/09/2022     17:54                EvenFolder                                                                                         



PS C:\> New-Item -ItemType Directory -Path c:\OddFolder


    Répertoire : C:\


Mode                 LastWriteTime         Length Name                                                                                               
----                 -------------         ------ ----                                                                                               
d-----        20/09/2022     17:55                OddFolder                                                                                          



PS C:\> Move-Item -Path File7 -Destination c:\OddFolder
Move-Item : Impossible de trouver le chemin d'accès « C:\File7 », car il n'existe pas.
Au caractère Ligne:1 : 1
+ Move-Item -Path File7 -Destination c:\OddFolder
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (C:\File7:String) [Move-Item], ItemNotFoundException
    + FullyQualifiedErrorId : PathNotFound,Microsoft.PowerShell.Commands.MoveItemCommand
 

PS C:\> Move-Item -Path C:\File7 -Destination c:\OddFolder
Move-Item : Impossible de trouver le chemin d'accès « C:\File7 », car il n'existe pas.
Au caractère Ligne:1 : 1
+ Move-Item -Path C:\File7 -Destination c:\OddFolder
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (C:\File7:String) [Move-Item], ItemNotFoundException
    + FullyQualifiedErrorId : PathNotFound,Microsoft.PowerShell.Commands.MoveItemCommand
 

PS C:\> Set-Location -Path C:\FolderTest1

PS C:\FolderTest1> Get-ChildItem


    Répertoire : C:\FolderTest1


Mode                 LastWriteTime         Length Name                                                                                        
----                 -------------         ------ ----                                                                                        
-a----        20/09/2022     17:31              0 File1                                                                                       
-a----        20/09/2022     17:31              0 File2                                                                                       
-a----        20/09/2022     17:31              0 File3                                                                                       
-a----        20/09/2022     17:31              0 File4                                                                                       
-a----        20/09/2022     17:31              0 File5                                                                                       



PS C:\FolderTest1> Move-Item -Path file1 -Destination c:\OddFolder

PS C:\FolderTest1> Set-Location -Path C:\OddFolder

PS C:\OddFolder> Get-ChildItem


    Répertoire : C:\OddFolder


Mode                 LastWriteTime         Length Name                                                                           
----                 -------------         ------ ----                                                                           
-a----        20/09/2022     17:31              0 file1                                                                          



PS C:\OddFolder> Set-Location -Path C:\FolderTest1

PS C:\FolderTest1> Move-Item -Path file3 file5 -Destination c:\OddFolder
Move-Item : Impossible de trouver un paramètre positionnel acceptant l'argument « file5 ».
Au caractère Ligne:1 : 1
+ Move-Item -Path file3 file5 -Destination c:\OddFolder
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidArgument : (:) [Move-Item], ParameterBindingException
    + FullyQualifiedErrorId : PositionalParameterNotFound,Microsoft.PowerShell.Commands.MoveItemCommand
 

PS C:\FolderTest1>  Move-Item -Path File3 -Destination c:\OddFolder

PS C:\FolderTest1>  Move-Item -Path file5 -Destination c:\OddFolder

PS C:\FolderTest1>  Move-Item -Path file2 -Destination c:\EvenFolder

PS C:\FolderTest1> Move-Item -Path File4 -Destination c:\EvenFolder

PS C:\FolderTest1> Set-Location -Path C:\FolderTest2

PS C:\FolderTest2> Get-ChildItem


    Répertoire : C:\FolderTest2


Mode                 LastWriteTime         Length Name                                                                                                                                     
----                 -------------         ------ ----                                                                                                                                     
-a----        20/09/2022     17:31              0 File10                                                                                                                                   
-a----        20/09/2022     17:31              0 File6                                                                                                                                    
-a----        20/09/2022     17:31              0 File7                                                                                                                                    
-a----        20/09/2022     17:31              0 File8                                                                                                                                    
-a----        20/09/2022     17:31              0 File9                                                                                                                                    



PS C:\FolderTest2> Move-Item -Path File6 -Destination c:\EvenFolder

PS C:\FolderTest2> Move-Item -Path File8 -Destination c:\EvenFolder

PS C:\FolderTest2> Move-Item -Path File10 -Destination c:\EvenFolder

PS C:\FolderTest2> Move-Item -Path File7 -Destination c:\OddFolder

PS C:\FolderTest2> Move-Item -Path File9 -Destination c:\OddFolder

PS C:\FolderTest2> Set-Location -Path C:\EvenFolder

PS C:\EvenFolder> Get-ChildItem


    Répertoire : C:\EvenFolder


Mode                 LastWriteTime         Length Name                                                                                                                                     
----                 -------------         ------ ----                                                                                                                                     
-a----        20/09/2022     17:31              0 File10                                                                                                                                   
-a----        20/09/2022     17:31              0 file2                                                                                                                                    
-a----        20/09/2022     17:31              0 File4                                                                                                                                    
-a----        20/09/2022     17:31              0 File6                                                                                                                                    
-a----        20/09/2022     17:31              0 File8                                                                                                                                    



PS C:\EvenFolder> Set-Location -Path C:\FolderTest1

PS C:\FolderTest1> Get-ChildItem

PS C:\FolderTest1> Get-ChildItem

PS C:\FolderTest1> 
