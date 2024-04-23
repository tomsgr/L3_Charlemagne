**Attention**, ce document est en cours de rédaction. Il s'agit d'une version de travail amenée à évoluer.

# Présentation du corpus

## Quel corpus pour quelles questions ? (Lola)

- Ce passage doit reprendre des éléments du DM du 26 mars sur la présentation du protocole de constitution du corpus.
- Il faut intégrer des graphiques obtenus sur Gallicagram et/ou Ngram Viewer.

![Courbe Gallicagram](img/Courbe_Gallicagram.png)

## Explorer le corpus des mentions de Charlemagne dans le Journal des Débats (Tom)

- présenter l'environnement logiciel : R, RStudio, quanteda
- présenter le code qui permet d'importer le corpus du journal des débats 1815-1870
- décrire les principales caractéristiques du corpus (nombres de mots et d'occurrences) et la distribution des mots selon la temporalité

# La question de la temporalité

## Position du problème et méthodologie (Tom et Lola)

- Reprendre la question de la temporalité dans le corpus à travers la présentation de la démarche allant de la table lexicale à l'AFC
- Rappeler brièvement ce qu'est une AFC
- Présenter AnalyseSHS
- Nombre de facteurs à dépouiller
- Seuillage des modalités, modalités en supplémentaire...

![Graphique factoriel](img/afc_charlemagne.png)

### Dépouillement du 1er facteur (Enzo)

#### La question romaine : usages discursifs défensifs et offensifs de Charlemagne

##### Introduction

Lors du *Risorgimento* une grande question a été l’objet d’une
controverse politique, dipliomatique et morale entre le Second Empire
français, le jeune Royaume d’Italie et les Etats Pontificaux. Elle
consistait à statuer sur le sort de Rome au sein ou à l’extérieur du
royaume d’Italie réunifié en 1861. Dans le *Journal des Débats*, côté
français, cette controverse s’est traduite par une hausse des usages
discursifs de Charlemagne en lien avec certains termes “Saint-Siège”,
“indépendnace”, “Rome”, “Eglise”, “souverain”, “Pape”, “France”,
“Italie” ou encore “Europe” comme cela est observable dans le premier
facteur dans notre Analyse factorielle des correspondances au sein des
coordonnées négatives. Ces coordonnées négatives réunissaient ces termes
ainsi que certaines années: 1860, 1861, 1865 et 1866. Il apparaît après
dépouillements des concordances de ces termes un double usage discursif
de Charlemagne. Le premier est défensif, c’est-à-dire qu’il vise à
défendre les droits territoriaux du pape, le second est offensif,
c’est-à-dire qu’il vise à contredire la position précédemment tenue. En
nous intéressant à quelques termes de notre analyse nous nous
interrogerons sur la référence historique à Charlemagne comme moyen de
défense d’une institution multiséculaire et comme moyen de promotion
d’une nouvelle identité italienne.

##### Un usage discursif de Charlemagne: défendre par un droit coutumier multiséculaire issu de l’histoire.

###### Un usage historique postulant un fondement juridique

Dans le *Journal des débats* une ligne éditoriale apparaît, celle de la
défense des droits territoriaux du pape : on repère en effet sur le 1er
facteur parmi les modalités lignes en coordonnées négatives les plus
fortes des mots comme “siège”, “Rome”, “Eglise” ou encore
“indépendance”. On constate que sur ce même facteur également en
coordonnées négatives parmi les modalités colonne les années “1860”,
“1861”, “1865” et “1866”. Nous pouvons également le voir dans un autre
temps en faisant une analyse des concordances de Rome en 1866. Sur R
Studio, pour faire apparaître ce résultat nous utilisons cette ligne de
code:

``` r
subcorpus <- corpus_subset(debats, annee == "1866")
toks_1866 <- tokens(subcorpus)
kwic(toks_1866, "religion", window=10)
```

    ## Keyword-in-context with 0 matches.

Cette ligne de code nous permet de faire apparaître dix mots avant et
après la forme pôle “Rome” dans les numéros du Journal des Débats de
l’année 1866.

Cette ligne se fonde sur plusieurs références historiques tissant un
lien profond entre Charlemagne et les Etats Pontificaux. Cela peut se
lire, dans le numéro du 1er décembre 1866, dans un article de P.David
traitant des nouvelles diplomatiques reçues de Naples le 24 novembre
1866 :

> “Charlemagne en constituant l’Etat pontifical n’en fit la donation
> qu’à Saint-Pierre et à la république, *beato Petro er romane
> reipublicae*” [^1]

Ici la référence historique est fausse, puisque c’est Pépin le Bref qui
a en réalité, en 751, réalisé la donation territoriale au Pape fondant
les Etats Pontificaux. Cependant, l’exclusivité de ce lien entre
“Charlemagne” et “Saint-Pierre”, à comprendre comme les successeurs de
Saint-Pierre, évêque de Rome et donc les papes, tisse de fait un lien
historique multiséculaire créant de fait une relation juridique de type
droit coutumier. Cette défense s’inscrit donc dans une tradition qui
reconnaît aux papes la jouissance du temporel en plus de la jouissance
d’une autorité spirituelle.

###### Un usage historique se fondant sur une défense morale

Cette défense qui se base sur un élément juridique fait aussi ressortir
le critère de l’indépendance, comme l’illustre cette citation dans le
numéro du 26 novembre 1866, citation extraite d’un article du
journaliste P.David:

> “Quoi qu’il en soit l’auteur commence par établir, d’après l’historien
> Muratori, que Rome n’ayant été conquise par les Lombards, n’a pu être
> comprise au nom des cités données ou restitues aux Papes par Pépin et
> Charemagne”.[^2]

Cette citation faisant référence au don de Pépin en 751, cre une nuance
insistant sur l’indépendance de la Ville Eternelle face aux Lombards
lors des conflits opposant rois lombards et papes dans les années 720 à
750. Ici, comme la ville n’a jamais été conquise et donc jamais
restituée, elle a donc toujours été indépendante. C’est cette
indépendance qui est défendue par le journaliste et rédacteur de la
colonne. Ainsi se crée une distinction entre la conquête qui donne au
vainqueur le sort du vaincu et dans un contexte où Rome n’a pas été
conquise par les troupes de Victor-Emmanuel II, de fait Rome peut garder
son indépendance.

##### Conclusion de sous-partie

Ainsi nous avons vu que par un usage historique créant une défense
juridique et morale des droits territoriaux du Pape. Cela traduit tous
les liens historiques entre Charlemagne et les papes qui de fait se sont
matérialisés sur le long temps historiques par l’émergence d’un acteur
pontifical spirituel et politique ayant influencé la politique
européenne durant de très longs sicèles.

##### Un usage discursif de Charlemagne offensif: la fin des Etats Pontificaux

###### La fin des Etats Pontificaux comme fin de l’unification italienne

Dans le *Journal des débats* une autre ligne éditoriale concurrente
celle de la réfutation des droits territoriaux du Saint-Siège. Cela
prend plusieurs formes. La première est celle d’une critique de la
désunion de l’Italie. Elle se lit dans le numéro du 19 novembre 1866
dans un éditorial de John Lemoinne qui lors de ce passage fait une
référence au *Discours sur Tite-Live* de Machiavel:

> “Comme quelques-uns pensent que la prospérité de l’Italie tient à
> l’existence de l’Eglise de Rome, qu’il me soit permis d’apporter
> contre cette opinion quelques raisons. Un pays ne peut être
> véritablement uni et prospérer que l’orsqu’il obéit à une seule espèce
> de gouvernement soit monarchie soit République. \[…\] Si le
> gouvernbement de l’Italie n’est pas ainsi oprganisé. \[…\] C’est à
> l’Eglise que nous le devons. Ainsi elle appela Chgarlemagne pour
> chasser les Lombards déjà rois de toute l’Italie. \[…\]. Telle est la
> cause de sa désunion. \[…\] Or tout cela c’est à la cour de Rome que
> nous le devons.” [^3]

Cette citation, prenant place dans un contexte de *Risrogimento*, cause
populaire en Europe, peut traduire une critique anticléricale qui est
facteur de désunion, puisque les Etats Pontificaux sont depuis 1866 le
dernier territoire *stricto sensu* italien à ne pas être rattaché au
jeune royaume. Cela illustrre toute l’ambiguïté du processus
d’unification qui paraît incomplet alors qu’il est dans sa phase
optimale de réalisation. Ici, il y a un rejet très fort d’une autorité
temporelle spirituelle, dans un contexte français où malgré l’appui sur
la religion du régime impérial, une partie de l’opposition défend des
thèses anticléricales souhaitant diminuer l’influence de m’Eglise dans
la société, en particulier dans le politique.

###### La Fin des Etats Pontificaux comme fin d’un acteur déliquescent

Une autre idée défendue au sein d’une partie de la rédaction du Journal
des Débats consiste à voir la fin de l’indépendance des Etats
Pontificaux comme la fin d’un acteur politique deliquescent ayant perdu
de sa superbe au cours des siècles passés et représnetant désormais une
sorte d’anachronisme politique. Cela nous est témoigné dans le numéro du
14 mars 1861, tirée d’un éditorial de John Lemoinne:

> “Le Saint-Siège ne veut pas transiger, il demande qu’avant tout son
> droit soit reconnu en se réservant d’en faire ensuite l’usage qu’il
> voudra \[…\] \[Le Duc de Valmy\] démontre aussi clairement que depuis
> longtemps la puissance temporelle du Saint-Siège a pêrdu le rang
> qu’elle occupait dans l’Equilibre politique de l’Europe; que la
> liberté et l’indépendance qu’elle possédait aux temps de Charlemagne
> et de Jules II ont été effacées par les transformations politiques et
> territoriales des deux derniers siècles” [^4]

Cette citation témloigne des évolutions géopolitiques internationles des
deux derniers diècles ayant progressivement rétrogradé les Etats
Pontificaux comme puissance minuere au sein de la péninsule italienne
soutenue surtout par de grands empires, le dernier en date étant
l’empire d’AUtriche au cours du XIXe siècle. Ainsi pour le Duc de Valmy,
il apparaît que l’indépendance pontificale est une position qui ne
puisse plus se défendre du fait du manque d’un soutien d’une grande
puissance. C’est dans cette pensée que se love le journaliste.

###### La fin des Etats Pontificaux: un usage de réalisme politique de la référence à Charlemagne

Un autre exemple pour réfuter la thèse de la défense de l’indépendnace
territoriale du pape, consiste en un retournement de la référence
historique à Charlemagne pour en faire non pas une tradition
multiséculaire reposant sur une sorte de respect spirituel, mais à en
faire une sorte d’accord de circonstance proche du réalisme politique.
Cela peut se voir dans l’analyse des concordances de politique en 1866
réaisée grâce à cette ligne de code sur R Studio.

``` r
subcorpus <- corpus_subset(debats, annee == "1866")
toks_1866 <- tokens(subcorpus)
kwic(toks_1866, "politique", window=10)
```

    ## Keyword-in-context with 5 matches.                                                                            
    ##  [81, 174] l'auteur conclut en disant qu'il s'agit d.e rétablir ce pouvoir |
    ##  [91, 164]                    spirituelle aux intérêts ^ dé"" son; pouvoir |
    ##  [92, 496]           , vice-prèsidont du Conseil d'Eiat, r < répond qu'une |
    ##  [92, 560]              exprimés par l'honorable M. Jules Favre, que cette |
    ##  [93, 131]                des deux autres, que l'honorable orateur est, en |
    ##                                                             
    ##  politique | et indépendant, et que c'est sous ses""        
    ##  politique | , que deviendrait, 1a fameuse formule, que «   
    ##  politique | sénsee qui, dès, le pr-incipo, ri a            
    ##  politique | est celle qui a été suivie par l'Empereur t (  
    ##  politique | , pour les émolliens. Il s'agit de résoudre les

L’analyse des concordances montrent cinq résultats témoignant à la fois
de l’enjeu politique de ce maintien le transformant en événement
politique circonstanciel influençant tant la politique extérieure
qu’intérieure du Second Empire. C’est ce qui est montré dans le numéro
du 19 mars 1866, citation tirée d’un commentaire d’actualités étrangères
à propos de la convocation d’un consistoire par le pape en janvier 1866.

> “Si l’on apprenait qu’en cette occasion le Saint-Siège avait sacrifié
> son in dépendnace spiritituelle aux intérêts de son pouvoir politique,
> que deviendrait la, fameuse formule, que”le pouvoir temporel assure
> l’indépendance du Pontife?” \[…\] Afin de s’assurer de la donation de
> Charlemagne, la papauté laisse épouser successivement neuf femmes, au
> mépris des arrêts énergiques par lesquels l’Eglise réprouvait le
> divorce” [^5]

Cette citation usant d’un exemple prosaïque pour démontrer les intérêts
politiques pour les deux partis à s’allier, renverse une sorte d’image
mieilleuse d’une alliance de principes entre Charlemagne et le pape. De
fait, la référence à Charlemagne est explicitée selon une analyse de
réalisme politique visant à démontrer qu’en fait le pape a toujours eu
besoin de protecteurs et qu’il était prêt à reneir sur les principes
religieux pour en obtenir. Ce choix renverse la défense morale de
l’indépendance des Etats Pontificaux puisque le lien entre Charlemagne
et religion est brisé. Cela peut nous amener plus loin que le simple
usage discursif de Charlemagne pour justifier ou non l’indépendnace des
Etats Pontificaux, nous pouvons montrer qu’en fait Charlemagne est
l’outil rhétorique moral servant à justifier de fait ce qui est une
volonté politique française. Cela est démontré de deux manières. La
première si on regarde les concordances de politique en 1861 avec le
code suivant:

``` r
subcorpus <- corpus_subset(debats, annee == "1861")
toks_1861 <- tokens(subcorpus)
kwic(toks_1861, "politique", window=10)
```

    ## Keyword-in-context with 10 matches.           
    ##  [191, 159]
    ##    [203, 5]
    ##  [209, 208]
    ##  [210, 124]
    ##  [210, 145]
    ##  [210, 151]
    ##    [214, 6]
    ##   [214, 48]
    ##   [215, 77]
    ##  [218, 295]
    ##                                                                         
    ##                       temps nous avons dit qu'au point de vue moral et |
    ##                                              J'applaudis vivement a la |
    ##       du Saint-Siège a perdu le rang qu'elle occupait dans l'équilibre |
    ##                           en même temps il a voulu, conformément iz la |
    ##      italiennes. Voyons la différence considérable qui existe entre la |
    ##                       qui existe entre la politique de l'Empire et, la |
    ##                                                        Il n'y a pas de |
    ##                                , pour sortir de cet état, revenir à la |
    ##                          mains du roi lombard que nous avons t'ait. La |
    ##  la France opposa aux raisonnemens l'instinct infaillible de son génie |
    ##             
    ##  politique |
    ##  politique |
    ##  politique |
    ##  politique |
    ##  politique |
    ##  politique |
    ##  politique |
    ##  politique |
    ##  politique |
    ##  politique |
    ##                                                                        
    ##  , cette neutralité recevrait une grave atteinte, et que               
    ##  de Napoléon III. <• En dégageant le Pape                              
    ##  de l'Europe que la liberté et l'indépendance qu'elle possédait aux    
    ##  séculaire de la France, maintenir la séparation des nations           
    ##  de l'Empire et, la politique révolutionnaire que j'ai signaléé        
    ##  révolutionnaire que j'ai signaléé. Napoléon 111 avait compris qu'il   
    ##  arrêtée, les documents en sont la preuue certaine;                    
    ##  dont nous avons dévié depuis Villafranca. Nous n'aurions pas          
    ##  française, les intérêts français y trouveraient uno satisfaction qu'il
    ##  et chrétien et aux armées d'une démocratie trompeuse elie opposa

Cette ligne de code montre que l’alliance entre Napoléon III et le Pape
est une alliance d’intérêt politique. Le deuxième témougnage de cette
idée se trouve dans cette citation du numéro du 12 mars 1861, tirée d’un
compte-rendu de la séance du Corps Législatif du 11 mars 1861:

> « Il \[L’Empereur\] a voulu maintenir deux intérêts éminemment
> français. Il a voulu maintenir la papauté dans des conditions de
> dignité et d’indépendance, et en même temps il voulut, conformément à
> la politique séculaire de la France, maintenir la séparation des
> nations italiennes. » [^6]

Ainsi, Charlemagne sert à justifier par l’histoire, la tradition ou la
morale une position qui peut sembler trahir nos alliés italiens du
moment, à savoir le choix de nuire à l’unification totale de l’Italie en
gardant les Etats du Pape selon un principe de respect envers la
religion.

##### Conclusion

En somme, dans le cadre de la question romaine, les usages discursifs de
Charlemagne montrent une certaine double appropriation de son image. La
première est celle relevant de la tradition historique du moment le
faisant le soutien infaillible du pape lui donnant des territoires et
lui permettant *in fine* de prendre son indépendnace et d’influer sur la
politique européenne. Cela traduit aussi le lien crée partout en Europe
entre l’action de Charlemagne et les dynamiques géopolitiques à l’oeuvre
au XIXe siècle dans la perspective de développement des nationalismes.
La seconde se construit en opposition à la première image tendant à
remettre du pragmatisme dans l’histoire, à accepter un certain niveau de
réel qui sert à la défense d’une cause jugée noble en son temps:
l’unification italienne. Au terme de cette réflexion nous pouvons ainsi
démontrer toute la plasticité de la figure de Charlemagne qui sert à
justifier tout et son contraire, montrant bien que Charlemagne relève du
mythe fondateur que du mythe en mouvement dans une réalité changeante.

[^1]: *Journal des débats*, 1er décembre 1866, lien
    URL:<https://gallica.bnf.fr/ark:/12148/bpt6k456344g>.

[^2]: *Journal des Débats*, 26 novembre 1866, URL:
    <https://gallica.bnf.fr/ark:/12148/bpt6k4563391>

[^3]: *Journal des Débats* 19 novembre 1866, URL:
    <https://gallica.bnf.fr/ark:/12148/bpt6k456332c>

[^4]: *Journal des Débats*, 14 mars 1861, URL:
    <https://gallica.bnf.fr/ark:/12148/bpt6k452639v>

[^5]: *Journal des Débats*, 19 mars 1866, URL:
    <https://gallica.bnf.fr/ark:/12148/bpt6k456090r>

[^6]: *Journal des Débats*, 12 mars 1861, URL:
    <https://gallica.bnf.fr/ark:/12148/bpt6k4526373>




### Dépouillement du 2e facteur (Alexandre)

- Présenter les principaux éléments mis en avant par le 2e facteur
- Il faut intégrer des retours au texte afin d'illustrer les observations faites via l'utilisation de la fonction `kwic()` de quanteda par exemple.
- Possibilité aussi de revenir aux journaux sur Gallica.

### Dépouillement du 3e facteur (Waldeck)

- Présenter les principaux éléments mis en avant par le 3e facteur
- Il faut intégrer des retours au texte afin d'illustrer les observations faites via l'utilisation de la fonction `kwic()` de quanteda par exemple.
- Possibilité aussi de revenir aux journaux sur Gallica.

# La question des genres journalistiques (selon le temps)

## Position du problème et méthodologie

## Principaux résultats
