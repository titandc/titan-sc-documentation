# Titan-sc-cli snapshot rotate

[_TOC_]

## Français

*Cette procédure permet d'expliquer comment effectuer des snapshots automatiques sur des machines Windows à partir de l'outil en ligne de commande [titan-sc](https://github.com/titandc/titan-sc-cli).*

### Installation de l'outil `titan-sc`

La documentation d'installation se trouve [ici](https://github.com/titandc/titan-sc-cli).

L'outil en ligne de commande a été installé dans le répertoire `C:\Program Files\titan-sc\`.

Après la configuration de l'outil via la commande `titan-sc setup`, le fichier de configuration `config` se trouve dans le répertoire `C:\Program Files\titan-sc\`.

### Créer la tâche planifiée

Ouvrir le planificateur de tâche de Windows.

Créer une tâche :

<img src="/assets/img/windows-create-task-description.png" width="500"/>

Ajouter un élément de déclenchement. Le temps entre deux snapshots est de 30 minutes minimum.

<img src="/assets/img/windows-create-trigger.png" width="500"/>

Ajouter une action :

<img src="/assets/img/windows-create-action.png" width="500"/>

* `Program/script` : Chemin complet vers le binaire `titan-sc.exe`. Dans l'exemple : `C:\Program Files\titan-sc\titan-sc.exe`
* `Add arguments (optional)` : Arguments du binaire pour permettre l'exécution de la commande choisi. Ici : `snapshot rotate --server-uuid "<server_uuid>" -f`
* `Start in (optional)` : Répertoire d'exécution de la tâche. Dans notre cas, il est nécessaire de remettre le chemin où se trouve le binaire pour permettre la lecture du fichier de configuration : `"C:\Program Files\titan-sc\"`

Valider la création de la tâche.

*Vous pouvez tester le lancement de la tâche en cliquant sur le bouton `Run` sur le panneau de droite pour vérifier qu'elle fonctionne à condition que votre prochain snapshot soit dans plus de 30 minutes.*

Le snapshot se créé et est visualisable sur l'interface Titan SmallCloud.

## English

*This procedure explains how to take automatic snapshots on Windows machines from the [titan-sc](https://github.com/titandc/titan-sc-cli) command line tool.*

### Installation of the `titan-sc` tool

Installation documentation can be found here [here](https://github.com/titandc/titan-sc-cli).

The command line tool has been installed in the `C: \ Program Files \ titan-sc \` directory.

After configuring the tool via the `titan-sc setup` command, the `config` configuration file is located in the `C: \ Program Files \ titan-sc \` directory.

### Create the scheduled task

Open the Windows Task Scheduler.

Create a task:

<img src="/assets/img/windows-create-task-description.png" width="500"/>

Add a trigger element. The time between two snapshots is at least 30 minutes.

<img src="/assets/img/windows-create-trigger.png" width="500"/>

Add an action

<img src="/assets/img/windows-create-action.png" width="500"/>

* `Program/script` : Full path to the `titan-sc.exe` binary. In the example: `C:\Program Files\titan-sc\titan-sc.exe`
* `Add arguments (optional)` : Arguments of the binary to allow the execution of the chosen command. Here: `snapshot rotate --server-uuid "<server_uuid>" -f`
* `Start in (optional)` : Directory for executing the task. In our case, it is necessary to set again the path where the binary is located to allow reading of the configuration file: `"C:\Program Files\titan-sc\"`

*You can test the launch of the task by clicking on the `Run` button on the right panel to verify that it works provided your next snapshot is in more than 30 minutes.*

Validate the creation of the task.

The snapshot is created and can be viewed on the Titan SmallCloud interface.
