# Titan-monitoring

- [Titan-monitoring](#titan-monitoring)
  - [Français](#français)
    - [Redémarrer la machine](#redémarrer-la-machine)
    - [Installer l'outil](#installer-loutil)
  - [English](#english)
    - [Restart the machine](#restart-the-machine)
    - [Installation of the tool](#installation-of-the-tool)

## Français

Afin de bénéficier de l'ensemble des statistiques présentes sur la dashboard de Titan SmallCloud, il est dorénavant nécessaire d'installer un service sur Linux/FreeBSD.

*Les machines ayant été créées ou réinitialisées après le 10 Mars 2021 intègrent déjà l'outil de monitoring de façon native, il 'est donc pas nécessaire de réaliser cette opération sur ces dernières.*

### Détecter les machines qui ne bénéficient pas encore de l'outil de monitoring

L'ensemble des machines dont les données de monitoring sont manquantes remontent les gauges suivantes :

<img src="/assets/img/missing-metrics.png" width="700"/>

### Installer l'outil

Il est nécessaire de se connecter sur votre machine Titan, de préférence en utilisant le protocole SSH plutôt que par le KVM (*il n'est pas possible de faire un copier/coller dans un KVM*).

La commande suivante doit être exécutée :

```bash
curl -fsSL https://repo.titandc.io/monitoring-client/install.sh | sh /dev/stdin $OSTYPE
```

Si la commande `curl` n'est pas installée, l'outil `wget` peut être également utilisé :

```bash
wget -q https://repo.titandc.io/monitoring-client/install.sh -O - | sh /dev/stdin $OSTYPE
```

Le service `titan-monitoring-client` est maintenant lancé. Les statistiques sur l'interface Titan SmallCloud seront automatiquement remontées sur votre dashboard. Si ce n'est pas le cas, la machine doit alors être redémarrée comme expliqué ci-dessous.


### Redémarrer la machine

*Si la machine a été redémarrée après la date du 10 mars 2021, cette étape est facultative.*

Si vous avez le moindre doute, redémarrez la machine. Une machine qui n'aura pas été redémarrée ne verra pas ses statistiques remonter.

Il faut **impérativement** redémarrer la machine depuis l'interface Titan SmallCloud, un redémarrage *software* (via la commande `reboot` ou `shutdown -r` par exemple) n'est pas suffisante.

<img src="/assets/img/reboot.png" width="200"/>

---

## English

In order to benefit from all the statistics present on the Titan SmallCloud dashboard, it is now necessary to install a service on Linux/FreeBSD.

*Any new machine created or reinitialized after March 10, 2021 already integrate the monitoring tool natively, it is therefore unnecessary to follow this procedure.*

### Detect machines requiring manual installation

Only the machines reporting the following incomplete metric gauges are concerned by the operation:

<img src="/assets/img/missing-metrics.png" width="700"/>

### Installation of the tool

It is necessary to connect to your Titan machine, preferably using the SSH protocol rather than the KVM. *It is not possible to copy/paste into a KVM.*

The following command should be executed:

```bash
curl -fsSL https://repo.titandc.io/monitoring-client/install.sh | sh /dev/stdin $OSTYPE
```

If the `curl` command is not present on the system, you can also use `wget` istead:

```bash
wget -q https://repo.titandc.io/monitoring-client/install.sh -O - | sh /dev/stdin $OSTYPE
```

At the end of the installation procedure, the `titan-monitoring-client` is now running. Statistics will now be displayed on the Titan SmallCloud interface. If this is not the case, then you need to reboot your machine as explained below.

### Restart the machine

*If the machine has been restarted since March 10, 2021, this step is optional.*

A restart of the machine is required if it has not been restarted since March 10, 2021. This restart **must** be executed via the Titan SmallCloud interface. A *software* restart (eg. using `reboot` or `shutdown -r` commands) is not sufficient.

<img src="/assets/img/reboot.png" width="200"/>

