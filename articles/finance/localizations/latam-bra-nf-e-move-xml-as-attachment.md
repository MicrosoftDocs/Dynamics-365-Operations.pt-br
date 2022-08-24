---
title: Mover arquivos XML de NF-e como anexos
description: Este artigo explica como mover arquivos XML de NF-e do banco de dados do Microsoft Dynamics 365 Finance ou Dynamics 365 Supply Chain Management e disponibilizá-los como anexos.
author: gionoder
ms.date: 11/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: 2022-01-27
ms.dyn365.ops.version: 10.0.25
ms.custom: 97423
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 7bb0fb975c6d73cc4e990b39ea9b5a0c0455db74
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270614"
---
# <a name="move-nf-e-xml-files-as-attachments"></a>Mover arquivos XML de NF-e como anexos

[!include [banner](../includes/banner.md)] 


Quando as notas fiscais eletrônicas (NF-e) são emitidas, os arquivos XML são criados e armazenados em bancos de dados do Microsoft Dynamics 365 Finance e do Microsoft Dynamics 365 Supply Chain Management. Na localização brasileira, você pode usar o recurso **Mover XML da NF-e como anexo** para liberar o espaço do banco de dados que esses arquivos XML consomem.

Para um intervalo de datas e estabelecimento fiscal específicos, o recurso move os arquivos XML de NF-e do banco de dados Finance ou Supply Chain Management para o Armazenamento de Blobs da sua assinatura do Azure. Esse movimento disponibiliza os arquivos somente como anexos. Depois que os arquivos XML são movidos com êxito para o Armazenamento de Blobs, os arquivos originais são excluídos do banco de dados Finance ou Supply Chain Management. Portanto, o espaço de banco de dados usado por esses arquivos é liberado.

Siga estas etapas para habilitar o recurso **Mover XML da NF-e como anexo**.

1. No Finance ou Supply Chain Management, abra o espaço de trabalho **Gerenciamento de recursos**.
2. Na guia **Tudo**, procure e selecione o recurso **Mover XML da NF-e como anexo**.
3. Selecione **Habilitar agora**.

Siga estas etapas para mover os arquivos XML da NF-e como anexos.

1. Acesse **Contas a receber** \> **Notas fiscais** \> **Notas fiscais eletrônicas** \> **Mover arquivos XML da NF-e como anexos**.
2. Nos campos **Data inicial** e **Data final**, selecione as datas inicial e final.
3. No campo **ID do estabelecimento fiscal**, selecione um valor.
4. Selecione **OK**.

> [!IMPORTANT]
> Esse processo é reversível. Depois de mover os arquivos XML da NF-e, os usuários podem exibi-los somente selecionando **Anexos** na parte superior da página **Nota fiscal**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
