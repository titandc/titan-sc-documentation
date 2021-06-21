# Titan-sc-cli snapshot rotate

- [Titan-sc-cli snapshot rotate](#titan-sc-cli-snapshot-rotate)
  - [Français](#français)
    - [Installation de l'outil `titan-sc`](#installation-de-loutil-titan-sc)
    - [Créer la tâche planifiée](#créer-la-tâche-planifiée)
  - [English](#english)
    - [Installation of the `titan-sc` tool](#installation-of-the-titan-sc-tool)
    - [Create the scheduled task](#create-the-scheduled-task)

## Français

*Cette procédure décrit comment automatiser la création des snapshots de vos serveurs hébergées sur Titan SmallCloud depuis une machine Windows.*

### Installation de l'outil `titan-sc` (création de snapshots depuis la ligne de commande)

La documentation d'installation se trouve [ici](https://github.com/titandc/titan-sc-cli).

L'outil en ligne de commande est automatiquement installé dans le répertoire `C:\Program Files\titan-sc\`.

Après avoir réalisé la configuration via la commande `titan-sc setup`, le fichier de configuration `config` se situe dans le répertoire `C:\Program Files\titan-sc\`.

### Créer une tâche planifiée (automatisation des snapshots)

Ouvrir le planificateur de tâche de Windows.

Créer une tâche :

<img src="/assets/img/windows-create-task-description.png" width="700"/>

Ajouter un élément de déclenchement. Note: Le temps d'attente minimal entre deux snapshots est de 30 minutes.

<img src="/assets/img/windows-create-trigger.png" width="700"/>

Ajouter une action :

<img src="/assets/img/windows-create-action.png" width="700"/>

* `Program/script` : Chemin complet vers le binaire `titan-sc.exe`. Dans l'exemple : `C:\Program Files\titan-sc\titan-sc.exe`
* `Add arguments (optional)` : Arguments du binaire pour l'exécution de la commande choisi. Ici : `snapshot rotate --server-uuid "<server_uuid>" -f`
* `Start in (optional)` : Répertoire d'exécution de la tâche. Dans notre cas, il est nécessaire de renseigner le chemin où se situe le binaire pour permettre la lecture du fichier de configuration : `"C:\Program Files\titan-sc\"`

Valider la création de la tâche.

*Vous pouvez tester l'exécution de la tâche en cliquant sur le bouton `Run` sur le panneau de droite afin de vérifier que celle-ci fonctionne bien (attention à bien respecter un délai minimum de 30 minutes entre la prise de snapshots d'une même machine).*

Le snapshot créé est consultable depuis l'interface Titan SmallCloud.

## English

*This procedure explains how to take automatic snapshots of your servers hosted on Titan SmallCloud from a Windows machine.*

### Installation of the `titan-sc` tool (take snapshots from command line)

The installation documentation can be found here [here](https://github.com/titandc/titan-sc-cli).

By default, the command line tool is installed in the `C: \ Program Files \ titan-sc \` directory.

After configuring the tool via the `titan-sc setup` command, the `config` configuration file is located in the `C: \ Program Files \ titan-sc \` directory.

### Create the scheduled task

Open the Windows Task Scheduler.

Create a task:

<img src="/assets/img/windows-create-task-description.png" width="700"/>

Add a trigger element. The time between two snapshots is at least 30 minutes.

<img src="/assets/img/windows-create-trigger.png" width="700"/>

Add an action

<img src="/assets/img/windows-create-action.png" width="700"/>

* `Program/script` : Full path to the `titan-sc.exe` binary. In the example: `C:\Program Files\titan-sc\titan-sc.exe`
* `Add arguments (optional)` : Arguments/options of the binary to execute the chosen command. Here: `snapshot rotate --server-uuid "<server_uuid>" -f`
* `Start in (optional)` : Directory for task execution. In our case, it is necessary to set again the location of the binary folder in order to read the configuration file: `"C:\Program Files\titan-sc\"`

*You can test the execution of the task by clicking to the `Run` button on the right panel in order to verify that it actually works (please remember to wait at least 30 minutes between two consecutive snapshots of the same server).*

Validate the creation of the task.

The snapshot is now created and can be viewed on the Titan SmallCloud interface.
