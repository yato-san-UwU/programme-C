#include <stdio.h>
#include <stdlib.h>
#include <string.h>
                                                // fct2/4/6/8/10    5/5
    char chaine[300];       // variable globale
    int T;        //fct 2 pour affecter
    char A,N;    // procedure 4
    int oui=0;     // fct 8 pour affecter
    char mots[20];   // fct 8 pour affect
    int palo;       //fct6 pour affect la fct
    int choixfonction;    //pour le switch
    int trt;     // pour affecter le switch
    char mot[50];
    int pos;
    int b;      // var de confirmation de changement (fct 4, fct 5, fct 7)

int Taille(char cha[300]) //  fct 1taille chaine sans '\0'
{
    int i; // on peut juste faire i=strlen(cha));
	i=0;
	while(cha[i]!='\0'){
		i++;
	}

return i;
}

int nbrmot(char cara[300]) //fct 2 compte le nombre de mot
{
    int i,comp;   // variable locale
    comp =1; // i pour la chaine comp compteur de mot

    for(i=0;cara[i]!='\0';i++) //parcourire la chaine de caractere
    {
            if (cara[i]==' '||cara[i]=='\t'||cara[i]=='\n')
            {
                    comp++;
            }
    }
    if(comp<=1)
    {
    printf("\n-La phrase contient :%d mot\n",comp);
    }
    else
    {
    printf("\n-La phrase contient :%d mots\n",comp);
    }
    demande();
return comp;
}

int Num(char ch[300])    //  fct 3 Nb Car numérique
{
    int i;
	int Nb;
	i=0,Nb=0;
	while(ch[i]!='\0')
	{ if(ch[i]>='0' && ch[i]<='9')
	     {Nb++;}
	  i++;
    }
    printf("\n-Le nombre de caracteres numerique est:%d",Nb);
    demande();
return Nb;
}

void rpccara(char A, char N)    // procedure 4 remplace
{
	int i,nbc;  // i=indice du tableau , nbc compteur nombre caratere
    char copiechaine[300];
	printf("\n+Entrer le caractere que vous souhaitez remplacer:");
	scanf("%c",&A);
	scanf("%c",&A);

	printf("\n+Entrer le nouveau caractere:");
    scanf("%c",&N);
	scanf("%c",&N);
	//double affectation pour supprimer le \n qui se trouve à la fin du tampon du premier scan

	nbc=strlen(chaine); // avoir la longueur de la chiane de caractere
    strcpy(copiechaine,chaine);   // copie de la chaine principal pour ne pas voir de problemes
    printf("\n-La chaine devient : ");
	for(i=0;i<nbc;i++)
	{
		if( copiechaine[i] == A ) {copiechaine[i]=N;}

		printf("%c",copiechaine[i]);
	}
	printf("\n");
	printf("\n!Voulez vous utiliser le nouveau texte cree (1 pour oui): ");
	scanf("%d",&b);
	if(b==1)
    {
        strcpy(chaine,copiechaine);
    }
    printf("\n");
	demande();
}

void insert(char CH[300],char W[27],int pos)   // fct 5 Insère un mot à la position pos
{
	int i,j,t,l;
	char copie2chaine[300];
	printf("\n+Donnez un mot a inserer: ");
    scanf("%s",mot);

    printf("\n+Donnez la position d'insertion (la position 1 correspond a 0): ");
    scanf("%d",&pos);

    strcpy(copie2chaine,chaine);   // copie de la chaine pour pas changer la premier
	t=Taille(copie2chaine);
	l=Taille(W);
	//décalage
	j=t+1;
	while(j>=pos)
	{
		copie2chaine[j+l]=copie2chaine[j];
		j--;
	}
    //insertion
    for(i=0;i<=l-1;i++)
    {
    	copie2chaine[pos+i]=W[i];
	}
	printf("\n-Apres insertion, la chaine est: %s",copie2chaine);
	printf("\n");
	printf("\n!Voulez vous utiliser le nouveau texte cree (1 pour oui): ");
	scanf("%d",&b);
	if(b==1)
    {
        strcpy(chaine,copie2chaine);
    }
    printf("\n");
    demande();
}

int exist(char chaine[100])   // fct 6 existe
{
    char mott[20];
    char* v; // pout utiliser "strstr" qui est une fonction qui chercher un mot dans un caractere
    int oui; // pour renvoyer 1/0 a modifer hein
    oui=0;

    printf("\n+Entrer un mot a cherche dans la chaine: ");
    scanf("%s",mott);

    v=strstr(chaine, mott); // strstr chercher un mot dans une fonction
    if(v)
    {
         oui=1;
        printf("\n-Le mot cherche est trouver dans la chaine\n"); //changer le text
    }
    else
    {
         oui=0;
        printf("\n-Cette chaine de caractere ne contient pas le mot cherche\n"); //changer le text

    }
    demande();
return oui;
}

int Longmot(char ch[300], int pos)  // pour utiliser des fonction
{
    int i;
    int h;
    i=pos;

    while(ch[i]!='\0' & ch[i]!=' ')
        {i++;}

    h=i-pos;     //p : position
return h;
}

void remplace( int pos, char mot[27]) // fct 7
{
    int k, l, t, j;
    char copie3chaine[300];
    printf("\n+Donnez la position du mot a remplacer (la position 1 correspond a 0): ");
    scanf("%d",&pos);
    printf("\n+Donnez le mot remplacant:");
    scanf("%s",mot);

    strcpy(copie3chaine,chaine);   // copie de la chaine principal pour ne pas voir de problemes

    k=Longmot(copie3chaine, pos);
    l=Longmot(mot, 0);
    t=Taille(copie3chaine);

        //décalge
    if(k>l)
    {   //vers droite
        for(j=pos+k; j<=t; j++)    //t+1  pour déplacer même le '\à'
	            {
                    copie3chaine[j-(k-l)]=copie3chaine[j];
				}
    }
	  else if(k<l)
    {   //  vers gauche
        for(j=t+1; j>=pos+k; j--)
            {
                copie3chaine[j+(l-k)]=copie3chaine[j];
            }
    }
    //Recopier le mot
	  for(j=0; j<=l-1; j++)    //on s'arrête à l pour ne pas prendre le '\0' du mot
		   {copie3chaine[pos+j]=mot[j];}

    printf("\n-La chaine apres remplacement: %s", copie3chaine);
    printf("\n");
	printf("\n!Voulez vous utiliser le nouveau texte cree (1 pour oui): ");
	scanf("%d",&b);
	if(b==1)
    {
        strcpy(chaine,copie3chaine);
    }
    printf("\n");
    demande();
}

int palindrom(char mot[20])  // fct 8 palindrome
{

   // char chaine[300]; // pas utile
    int I,J;  //parcourire le mot
    int d;     // indicateur logique:       vrai si mot est un palindrome

    printf("\n+Entrer un mot pour savoir si celui ci est un palindrome : ");
    scanf("%s",mot);
                // Placer J sur la dernière lettre de la chaîne
    for(J=0; mot[J]; J++){} // avoir la taille de j = taille message (mot)
       J--; // pour avoir la vrai taille du message

    d=1;
    for (I=0 ;I<J ; I++,J--)
         if (mot[I]!=mot[J])
           {
                d=0;
           }
    if (d) //d comparer a 0
      {
        printf("\n-La chaine \"%s\" est un palindrome.\n", mot);
      }
    else{
        printf("\n-La chaine \"%s\" n'est pas un palindrome.\n", mot);
    }
    demande();
return d;
}

void motmax(char c[300], char Motmax[27])   // fct 9  Donne le mot le plus long de la chaine
{
    int i, j, l, pos, lmax;
    i=0; lmax=0;

      while(c[i]!='\0')
	  { while(c[i]==' '){ i++; }
	    if(c[i]!='\0')
		{ //Debut d'un mot C[i] 1er caractère du mot
		    pos=i;
		    l=Longmot(c, pos);
		    if(lmax<l)
			   {
                lmax=l;
                for(j=0; j<=l; j++){ Motmax[j]=c[pos+j];}
			   }
            i=i+l;	    //dépasser le mot courant
		}
	  }
     printf ("\n-Le mot le plus long est: %s",Motmax);
     demande();
}

void TV()               // procedure 10
{
    char T[300];
    int V[300]={0};  // T caractere V nbr
    int i,j,lg;    // i indice pour T j pour V lg ???

    T[0]=chaine[0];
    j=0;
    lg=0;
    while(chaine[j]!='\0')
    {
        i=0;
        while(chaine[j]!=T[i] && i<=lg)
        {
            i++;
        }
            if(chaine[j]==T[i])
            {
                V[i]++;
            }
            else
            {
                T[i]=chaine[j];
                lg++;
                V[i]++;
            }
        j++;
    }
    printf("\n");
    printf("-Le tableau sans repetition : ");
    puts(T); // tableau sans repetition
    for(i=0;i<=lg;i++)
    {
    printf("\n-T=\"%c\" V=%d",T[i],V[i]);  // tableau sans repetion + nombre doccurence
    }
    demande();
}

void menu()     // pour repeter la demande du choix de fonctions
{
    printf("\n\nVoila votre phrase : %s",chaine);
    printf("\n\nEntrer le numero de fonction : ");
    scanf("%d",&choixfonction);
switch(choixfonction)
 {
    case 1:
        printf("\n-La taille de la chaine est:%d", Taille(chaine));
        demande();
        break;
    case 2:
        T=nbrmot(chaine);// appel fonction2
    break;
    case 3:
        Num(chaine);    // appel fonction 3
    case 4:
         rpccara(A,N);     // appel procedure4
    break;
    case 5:
        insert(chaine,mot,pos);
        break;
    case 6:
        palo=exist(chaine); // appel fonction6
    break;
    case 7 :
        remplace(pos,mot);
    break;
    case 8:
        oui=palindrom(mots); // appel fonction8
    break;
    case 9 :
        motmax(chaine,mots);   // appel fonction 9
    case 10:
        TV();                  // appel procedure 10
    break;
    case 11:
        printf("\n\t\tFin du programme\n");
    break;
    default:
        printf("Votre choix de fonction nexiste pas\n");
        printf("Corriger votre choix: ");
        menu();
    break;
 }
}

void demande()   // pour eviter de repeter le message
{
    printf("\n\n\tAppuyez sur 1 pour continuer:");
    scanf("%d",&trt);
    printf("\n\n");
    printf("________________________________________________________________________");
    if(trt==1)
    {
        menu();
    }
    else
    {
        printf("\n\n\t\t+++Fin du programme+++\n\n");
    }
      printf("\n");
}

int main()   // fonction principal
{
    printf("Entrez votre phrase: ");
    gets(chaine);
    printf("\t***Choix de fonction a utiliser***\n\n");
    printf("\t1.Taille de la chaine\n\n");
    printf("\t2.Nombres de mots du texte\n\n");
    printf("\t3.Nombre de caracteres numeriques dans le text\n\n");
    printf("\t4.Remplacer un caractere par un autre\n\n");
    printf("\t5.Insertion d'un mot dans le text\n\n");
    printf("\t6.Rechercher un mot dans le text\n\n");
    printf("\t7.Replacer un mot par un autre\n\n");
    printf("\t8.Verifie si le mot est un palindrome\n\n");
    printf("\t9.Retourne le plus long mot de la chaine\n\n");
    printf("\t10.Generer deux vecteurs\n\n");
    printf("\t11.Quitter le programme\n________________________________________________________________________");
    menu();

    return 0;
}
