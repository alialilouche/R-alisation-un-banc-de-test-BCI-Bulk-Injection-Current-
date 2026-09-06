# 1. Introduction

&nbsp;&nbsp;&nbsp;&nbsp; Dans l’environnement industriel moderne, les équipements électroniques sont exposés à un niveau croissant de perturbations électromagnétiques. Cette pollution électromagnétique est particulièrement signifcative dans des environnements complexes tels que l’automobile et l’aéronautique, où coexistent de multiples sources d’émissions (convertisseurs de puissance, systèmes de communication, moteurs électriques, calculateurs embarqués, etc.). Ces perturbations peuvent altérer le fonctionnement normal des dispositifs électroniques et compromettre leur fabilité. La capacité d’un équipement à fonctionner correctement en présence de telles perturbations est définie comme son immunité électromagnétique. Parmi les phénomènes de perturbation les plus critiques figurent les perturbations conduites et rayonnées. Les perturbations conduites se propagent principalement à travers les câbles d’alimentation ou de communication, tandis que les perturbations rayonnées se transmettent par couplage électromagnétique dans l’espace environnant. Dans le domaine automobile notamment, les faisceaux de câblage constituent des chemins privilégiés pour la propagation des interférences, pouvant ainsi aﬀecter les calculateurs électroniques et les systèmes embarqués. Afin d’évaluer l’immunité des équipements face à ces phénomènes, des essais normalisés sont réalisés en laboratoire. Ces tests consistent à reproduire des conditions représentatives de l’environnement réel en injectant des perturbations contrôlées sur les câbles de l’équipement sous test (EST). Parmi ces essais, le test BCI (Bulk Current Injection) constitue une méthode largement utilisée pour l’évaluation de l’immunité conduite surtout en environnement automobile. Le principe de base de la méthode BCI repose sur l’injection d’un courant perturbateur haute fréquence dans les faisceaux de câbles via une pince d’injection, sans contact galvanique direct. Les essais sont réalisés conformément aux exigences normatives en vigueur dans chacun des domaines spécifque. Dans le cadre de ce projet, nous avons adopté une démarche méthodologique complète pour réaliser un processus de calibrage et de test d’une méthode BCI. Dans un premiers temps, nous défnissons les principaux équipements utilisés ainsi leurs qualifcation vis-à-vis les transparences électromagnétique à partir des études analytiques notamment les fonctions de transfert afn d’anticiper leur comportement face aux perturbations injectées. Ensuite la phase de calibrage de ces équipements nous serait indispensable, pour cela on commence par calibrer l’analyseur de réseau vectoriel (VNA),afin de passer au calibrage et la caractérisation des autres équipements. Une fois les données de ces caractéristiques sont relevées soigneusement, on procède à renseigner ces facteurs dans le logiciel de pilotage qui va nous assurer le bon calibrage de setup complet. Principalement, et conformément à la norme EN 61000-4-6 nous réalisons des essais selon trois niveaux de sévérité : 1V, 3V et 10V. Nous avons également la chance de réaliser deux essais d’immunité conduite avec le réseau de couplage et de découplage (CDN). Où on va pouvoir mener des études comparatives avec la pince d’injection.

# 2. Description du test BCI

&nbsp;&nbsp;&nbsp;&nbsp; Le test BCI est un essai d’immunité conduite utilisé en Compatibilité Électromagnétique (CEM) afin d’évaluer la robustesse d’un équipement électronique face aux perturbations radiofréquences. L’objectif est de reproduire le couplage électromagnétique susceptible d’apparaître entre un champ rayonné et le faisceau de câbles d’un système électronique. En environnement réel, les câbles peuvent se comporter comme des antennes réceptrices et conduire des courants perturbateurs vers l’équipement. Le test BCI permet de reproduire ce phénomène de manière contrôlée en injectant directement un courant RF dans le faisceau de câbles, afn d’analyser le comportement du système soumis à une contrainte représentative de son environnement électromagnétique.

## 2. 1. Principe de fonctionnement

&nbsp;&nbsp;&nbsp;&nbsp; Le principe du test consiste à injecter un courant haute fréquence dans le faisceau de câbles à l’aide d’une pince d’injection positionnée autour du câble. Cette pince fonctionne selon le principe d’un transformateur : l’enroulement interne alimenté par un générateur RF constitue le primaire, tandis que le câble traversant la pince joue le rôle de secondaire. Le couplage entre la pince et le câble est principalement inductif, tandis que le blindage de la pince permet de limiter le couplage capacitif. Le signal RF est d’abord généré puis amplifé avant d’être appliqué à la pince d’injection. On induit ainsi un courant de mode commun dans le faisceau de câbles. Ce courant se propage le long des conducteurs et peut perturber les circuits internes via les interfaces d’entrée et de sortie. L’essai permet donc d’observer le comportement du système face à une sollicitation électromagnétique conduite.

*Figure 1: Principe du test BCI*

![Figure 1: Principe du test BCI](Images/Principe_BCI.png)

## 2. 2. Procédure de test

&nbsp;&nbsp;&nbsp;&nbsp; Le test BCI se déroule généralement en deux étapes principales : la calibration puis l’injection. Dans un premier temps, on réalise une phase de calibration afn d’établir la relation entre la puissance appliquée à la pince et le courant réellement injecté. Cette calibration est eﬀectuée sur un montage de référence présentant une impédance connue en mode commun. On obtient ainsi une courbe de calibration sur l’ensemble de la plage fréquentielle considérée. Une fois cette étape validée, on procède à l’injection sur l’équipement sous test. On eﬀectue alors un balayage fréquentiel sur la plage défnie par la norme applicable. À chaque fréquence, on injecte le courant spécifé, on maintient le niveau pendant une durée déterminée, et on surveille le fonctionnement du système. Les éventuelles dégradations sont ensuite classées selon les critères de performance défnis par la norme.

*-* **Boucle ouverte (méthode de substitution)**:

La puissance appliquée à la pince d’injection est déterminée lors de la phase de calibration sur une charge de référence. Pendant l’essai, cette puissance est appliquée sans régulation active du courant. Le courant réellement injecté dépend donc de l’impédance du faisceau de câbles et peut varier en fonction de la fréquence. Cette méthode est simple à mettre en œuvre et rapide, mais elle reste sensible aux variations d’impédance et peut conduire à un sous-test à certaines fréquences d’antirésonance.

*-* **Boucle fermée (méthode asservissement)**:

Le courant injecté est mesuré en permanence à l’aide d’une pince de mesure. On compare ce courant à la valeur de consigne, et le système ajuste automatiquement la puissance du générateur afn de maintenir un courant de mode commun constant. Cette méthode oﬀre une meilleure précision et une meilleure reproductibilité. En revanche, à certaines fréquences, la puissance maximale disponible peut ne pas sufre à atteindre la consigne fxée.

# 3. Recommandations et normes

## 3. 1. Recommandations 

&nbsp;&nbsp;&nbsp;&nbsp; Les essais d’immunité par injection de courant (BCI) s’inscrivent dans le cadre général des normes de Compatibilité Électromagnétique (CEM). Lorsqu’on réalise un test BCI, on s’appuie obligatoirement sur un référentiel normatif qui défnit les conditions de test, les méthodes de mesure, les niveaux de sévérité ainsi que les critères d’acceptation. Le respect de ces normes permet d’assurer la reproductibilité des essais, la comparabilité des résultats entre laboratoires et la conformité réglementaire des équipements. On garantit ainsi que le niveau d’immunité validé correspond réellement à l’environnement d’utilisation du produit. Les exigences varient selon le domaine d’application. En fonction du secteur considéré, on n’a pas la même plage fréquentielle d’essai, ni les mêmes niveaux de courant injecté, ni les mêmes critères de performance. Les normes précisent également la méthode de calibration à utiliser, la confguration du banc d’essai et les modalités de surveillance du fonctionnement pendant le test.

# 3. 2. Normes de test BCI 

La méthode Bulk Current Injection est décrite dans plusieurs normes internationales.

*-* **Domaine automobile**:

La référence principale est la norme ISO 11452-4. Cette norme défnit la méthode d’essai par injection de courant à l’aide d’une pince d’injection. On y retrouve une plage fréquentielle généralement comprise entre 1 MHz et 400 MHz. La norme précise également la procédure de calibration, qui peut être réalisée en boucle ouverte ou en boucle fermée, ainsi que la disposition du faisceau de câbles pendant l’essai. Les dégradations observées sont ensuite classées selon des critères de performance normalisés

*-* **Domaine aéronautique**:

On se réfère principalement à la norme DO-160G, section 20. Elle traite des essais d’immunité aux radiofréquences conduites et rayonnées pour les équipements embarqués. Les niveaux de sévérité sont généralement plus élevés que dans le domaine automobile, car l’environnement électromagnétique est plus contraignant, notamment en présence de radars et de systèmes de communication haute puissance.

*-* **Circuits intégrés**:

On utilise la norme IEC 62132-3, qui adapte la méthode BCI aux composants électroniques de petite dimension. Même si le contexte diﬀère, on retrouve les mêmes principes fondamentaux : un couplage inductif via une pince, une calibration préalable et une surveillance continue du fonctionnement pendant l’essai.

### 3. 2. 1 La norme EN 61000-4-6

La norme EN 61000-4-6 défnit la méthode d’essai permettant d’évaluer l’immunité des équipements électriques et électroniques aux perturbations conduites induites par des champs radiofréquences. Elle fait partie de la série IEC 61000 relative à la compatibilité électromagnétique (CEM), et plus précisément de la partie 4 consacrée aux techniques d’essai et de mesure. Cette norme s’applique aux équipements comportant au moins un câble conducteur, tel qu’un cordon d’alimentation, une ligne de signal ou une connexion de masse, susceptible de capter des perturbations électromagnétiques. En eﬀet, sous l’eﬀet d’un champ radiofréquence, les câbles peuvent se comporter comme des antennes et véhiculer des courants de mode commun vers l’équipement. L’essai vise donc à simuler ce phénomène de manière contrôlée afn d’évaluer l’immunité fonctionnelle du matériel.

La norme EN 61000-4-6 est utilisée dans de nombreux secteurs où la robustesse électromagnétique est essentielle : domaine industriel, télécommunication et électronique grand public. Elle sert de référence aux normes de produit qui précisent les niveaux d’essai
et les critères de performance applicables à chaque type d’équipement. La plage de fréquences couverte par la norme est comprise entre 150 kHz et 80 MHz. Le signal d’essai est une onde radiofréquence modulée en amplitude à 80 % par une sinusoïde de 1 kHz, afn de reproduire des conditions réalistes d’exposition aux émetteurs radioélectriques. Les niveaux d’essai sont défnis en tension en circuit ouvert (force électromotrice) à l’accès de l’équipement et sont présentés dans le tableau suivant :

*Figure 2: Niveaux d’essai selon EN 61000-4-6*

![Figure 1: Niveaux d’essai selon EN 61000-4-6](Images/Principe_BCI.png)
