# Titan-monitoring

- [Titan-monitoring](#titan-monitoring)
  - [Français](#français)
    - [Installation de l'outil](#installation-de-loutil)
  - [English](#english)
    - [Installation of the tool](#installation-of-the-tool)

## Français

*Cette procédure est valable pour l'ensemble des OS Windows proposés par Titan SmallCloud.*

Afin de bénéficier de l'ensemble des statistiques présentes sur la dashboard de Titan SmallCloud, il est dorénavant nécessaire d'installer un service de monitoring sur Windows.

L'installation de l'outil `titan-monitoring` a été testé sur les versions suivantes de l'OS Windows à date du 28 avril 2021 :

* Windows 10 20h2
* Windows server 2012 r2
* Windows server 2016
* Windows server 2019

*Veuillez noter que pour l'instant, les binaires de l'outil `titan-monitoring` et de son installeur ne sont pas encore signés.*

### Installation de l'outil

Téléchargez l'outil de [monitoring](https://repo.titandc.io/monitoring-client/install-titan-mc.exe) sur votre machine Windows.

Trouvez l'emplacement où il a été enregistré puis exécutez-le, le message suivant va apparaître :

<img src="/assets/img/windows-security.png" width="500"/>

Une fois l'installation terminée, un service Windows sera automatiquement lancé. Les statistiques sont maintenant affichées sur l'interface Titan SmallCloud.

<img src="/assets/img/metrics.png" width="700"/>

---

## English

*This procedure is valid for all Windows OS delivered on Titan SmallCoud.*

In order to benefit from all the statistics shown in Titan SmallCloud dashboard, it is now necessary to install a monitoring service on Windows.

The installation of the `titan-monitoring` tool has been tested on the following Windows OS as of April 28, 2021:

* Windows 10 20h2
* Windows server 2012 r2
* Windows server 2016
* Windows server 2019

*Please note that, at this time, `titan-monitoring` and installation binaries are not yet signed.* 

### Installation of the tool

Download the [monitoring](https://repo.titandc.io/monitoring-client/install-titan-mc.exe) tool on your Windows machine.

Find the location where it was saved and then execute it, the following message will appear:

<img src="/assets/img/windows-security.png" width="500"/>

The installation will take place and once completed, a Windows service will be automatically launched. You should now have the statistics in your Titan SmallCloud interface.

<img src="/assets/img/metrics.png" width="700"/>

