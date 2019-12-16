---
title: Configuration requise pour Hyper-V sur Windows 10
description: Configuration requise pour Hyper-V sur Windows 10
keywords: Windows 10, Hyper-V
author: scooley
ms.date: 05/02/2016
ms.topic: article
ms.prod: windows-10-hyperv
ms.service: windows-10-hyperv
ms.assetid: 6e5e6b01-7a9d-4123-8cc7-f986e10cd372
ms.openlocfilehash: d4e3f7c1e94d0162ae9ee6251d9c6d8cc51bf1d3
ms.sourcegitcommit: 1ca9d7562a877c47f227f1a8e6583cb024909749
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/04/2019
ms.locfileid: "74911219"
---
# <a name="windows-10-hyper-v-system-requirements"></a>Configuration requise pour Hyper-V sur Windows 10

Hyper-V est disponible en version 64 bits de Windows 10 professionnel, entreprise et éducation. Hyper-V nécessite la technologie SLAT (Second Level Address Translation), présente dans la génération actuelle de processeurs 64 bits Intel et AMD.

Vous pouvez exécuter trois ou quatre machines virtuelles de base sur un hôte disposant de 4 Go de RAM. Pour exécuter plus de machines virtuelles, davantage de ressources sont nécessaires. En revanche, vous pouvez créer des machines virtuelles de grande taille avec 32 processeurs et 512 Go de RAM, selon votre matériel physique.

## <a name="operating-system-requirements"></a>Configuration requise pour le système d’exploitation

Le rôle Hyper-V peut être activé sur ces versions de Windows 10 :

- Windows 10 Entreprise
- Windows 10 Professionnel
- Windows 10 Éducation

Le rôle Hyper-V **ne peut pas** être installé sur :

- Windows 10 Famille
- Windows 10 Mobile
- Windows 10 Mobile Entreprise

>Windows 10 édition personnelle peut être mis à niveau vers Windows 10 professionnel. Pour cela, ouvrez **Paramètres** > **Mise à jour et sécurité** > **Activation**. Vous pouvez alors visiter le magasin et acheter la mise à niveau.

## <a name="hardware-requirements"></a>Configuration matérielle requise

Bien que ce document ne fournisse pas la liste complète du matériel compatible avec Hyper-V, vous devez disposer des éléments suivants :

- Processeur 64 bits avec traduction d’adresse de second niveau (SLAT).
- Processeur prenant en charge les extensions de mode du moniteur de machine virtuelle (VT-c sur les processeurs Intel).
- Au minimum 4 Go de mémoire. Étant donné que les machines virtuelles partagent la mémoire avec l’hôte Hyper-V, vous devez fournir suffisamment de mémoire pour gérer la charge de travail virtuelle attendue.

Les éléments suivants doivent être activés dans le BIOS du système :
- Technologie de virtualisation (cette appellation peut varier selon le fabricant de la carte mère).
- Prévention de l’exécution des données appliquée par le matériel.

## <a name="verify-hardware-compatibility"></a>Vérifier la compatibilité matérielle

Pour vérifier la compatibilité, ouvrez PowerShell ou une invite de commandes (cmd.exe), puis tapez **systeminfo**. Si tous les éléments de la configuration requise pour Hyper-V ont la valeur **Oui**, votre système peut exécuter le rôle Hyper-V. Si l’un des éléments a la valeur **Non**, passez en revue la configuration requise figurant dans ce document et apportez des ajustements dans la mesure du possible.

![](media/SystemInfo-upd.png)

Si vous exécutez **systeminfo** sur un hôte Hyper-V existant, la section Configuration requise pour Hyper-V indique ce qui suit :

```
Hyper-V Requirements: A hypervisor has been detected. Features required for Hyper-V will not be displayed.
```