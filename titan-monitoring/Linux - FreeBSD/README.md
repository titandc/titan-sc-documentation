# Titan-monitoring

- [Titan-monitoring](#titan-monitoring)
  - [Français](#français)
    - [Redémarrer la machine](#redémarrer-la-machine)
    - [Installer l'outil](#installer-loutil)
  - [English](#english)
    - [Restart the machine](#restart-the-machine)
    - [Installation of the tool](#installation-of-the-tool)

## Français

*Cette procédure ne s'applique que pour les machines ayant été créées (ou réinitialiséés) avant le 10 mars 2021 ou pour toutes les machines PLESK.*

*Toute nouvelle machine créée ou réinitialisée après le 10 mars 2021 et étant différente de PLESK comporte déjà l'outil nativement. Il n'est donc pas nécessaire de suivre cette procédure.*

Afin de bénéficier de l'ensemble des statistiques présentes sur la dashboard de Titan SmallCloud, il est dorénavant nécessaire d'installer un service sur Linux/FreeBSD.

Il est nécessaire de se connecter sur votre machine Titan, de préférence en utilisant le protocole SSH plutôt que par le KVM (*il n'est pas possible de faire un copier/coller dans un KVM*)

### Redémarrer la machine

*Si la machine a été redémarrée après la date du 10 mars 2021, cette étape est facultative.*

Un redémarrage de la machine est nécessaire dans le cas où elle n'a pas été redémarrée depuis le 10 mars 2021.

Il faut impérativement redémarrer la machine via l'interface Titan SmallCloud. Un redémarrage *software* (la commande `reboot` par exemple) n'est pas suffisant.

Si vous avez le moindre doute, redémarrez la machine. Une machine qui n'aura pas été redémarrée ne verra pas ses statistiques remonter.

### Installer l'outil

Une fois le redémarrage effectué, la commande suivante doit être tapée :

Si la commande `curl` est installée :

```bash
curl -fsSL https://repo.titandc.io/monitoring-client/install.sh | sh /dev/stdin $OSTYPE
```

Si la commande `curl` n'est pas installée :

```bash
wget -q https://repo.titandc.io/monitoring-client/install.sh -O - | sh /dev/stdin $OSTYPE
```

Le service `titan-monitoring-client` est maintenant lancé. Les statistiques sur l'interface Titan SmallCloud seront rafraichis.

## English

*This procedure only applies for machines that were created (or reset) before March 10, 2021 or for all PLESK machines.*

*Any new machine created or reinitialized after March 10, 2021 and being different from PLESK already includes the tool natively. It is therefore not necessary to follow this procedure.*

In order to benefit from all the statistics present on the Titan SmallCloud dashboard, it is now necessary to install a service on Linux/FreeBSD.

It is necessary to connect to your Titan machine, preferably using the SSH protocol rather than the KVM. *It is not possible to copy/paste into a KVM.*

### Restart the machine

*If the machine has been restarted since March 10, 2021, this step is optional.*

A restart of the machine is required if it has not been restarted since March 10, 2021. This restart must be executed via the Titan SmallCloud interface. A *software* restart (the `reboot` command for example) is not sufficient.

Statistics will not be displayed in the Titan SmallCloud dashboard if the machine has not been restarted.

### Installation of the tool

After restarting, the following command should be used:

If the `curl` command is present on the system :

```bash
curl -fsSL https://repo.titandc.io/monitoring-client/install.sh | sh /dev/stdin $OSTYPE
```

If the `curl` command is not present on the system :

```bash
wget -q https://repo.titandc.io/monitoring-client/install.sh -O - | sh /dev/stdin $OSTYPE
```

At the end of the installation procedure, the `titan-monitoring-client` is now running. Statistics will now be displayed on the Titan SmallCloud interface.
