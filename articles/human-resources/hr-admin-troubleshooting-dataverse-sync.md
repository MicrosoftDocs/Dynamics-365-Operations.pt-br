---
title: Redefinir a sincronização do Dataverse
description: Este tópico descreve como solucionar problemas de registros que não são sincronizados corretamente entre o Microsoft Dynamics 365 Human Resources e a solução HCM (Gerenciamento de capital humano) Common no Microsoft Dataverse.
author: jaredha
ms.date: 09/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-09-27
ms.dyn365.ops.version: Platform update 42
ms.openlocfilehash: d88f538fbf22313feaca6771b7cb1757a3c3fbad
ms.sourcegitcommit: 12e26ef25c492e5032260733b50cd642cbd6164d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2021
ms.locfileid: "7559625"
---
# <a name="reset-dataverse-synchronization"></a>Redefinir a sincronização do Dataverse

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="issue"></a>Problema

Os registros não são sincronizados entre o Microsoft Dynamics 365 Human Resources e as entidades da solução HCM (Gerenciamento de capital humano) Common no Microsoft Dataverse. Para obter mais informações sobre sincronização, acesse [Configurar a integração do Dataverse](hr-admin-integration-common-data-service.md). A falha em sincronizar corretamente pode ocorrer quando os trabalhos em lotes **Repetição da integração do Dataverse** ou **Sincronização de solicitação perdida da integração do Dataverse** ficam presos em um estado **Executando**.

## <a name="resolution"></a>Resolução

Quando os trabalhos em lotes **Repetição da integração do Dataverse** ou **Sincronização de solicitação perdida da integração do Dataverse** ficarem presos em um estado **Executando** ou **Cancelando**, você poderá redefinir o status. Isso pode ser feito com o cancelamento do trabalho em lotes seguindo as diretrizes em [Redefinir trabalhos em lotes presos](hr-admin-troubleshooting-batch-execution.md). Depois de cancelar o trabalho em lotes, você poderá redefinir o trabalho em lotes ao defini-lo para um status **Aguardando**. O trabalho em lotes será executado durante o próximo runtime programado.

1. Se você ainda não tiver feito isso, habilite o recurso **Anulação de lote aprimorada** em **Gerenciamento de recursos**.
   1. Vá para a página **Gerenciamento de recursos** (**Administração do sistema** > **Resumo** > **Gerenciamento de recursos**).
   2. Selecione a guia **Tudo**.
   3. Selecione a coluna **Nome do recurso** e filtre por **Anulação de lote aprimorada**.
   4. Selecione a ação **Habilitar** se ainda não estiver habilitada.

2. Desativar a integração do Dataverse.
   1. Acesse a página **Integração do Microsoft Dataverse** (**Administração do sistema**, acesse **Links** > **Integrações** > **Configuração do Dataverse**).
   2. Defina **Habilitar integração do Dataverse** como **Não**.

3. Cancele o trabalho em lotes **Repetição da integração do Dataverse**.
   1. Acesse a página **Trabalho em lotes** (**Administração do sistema**, acesse **Links** > **Trabalhos em lotes** > **Trabalhos em lotes**).
   2. Filtre a coluna **Descrição do trabalho** por **Integração**.
   3. Selecione o trabalho em lotes **Repetição da integração do Dataverse**.
   4. Na faixa de opções da ação, selecione **Trabalho em lotes**, **Forçar cancelamento** e, em seguida, selecione **Sim** para confirmar.

   > [!NOTE]
   > Dependendo de quando a integração foi habilitada pela primeira vez, o trabalho em lotes poderá ter a descrição **Repetição da integração do Common Data Service**. Selecione esse trabalho em lotes, caso ele esteja listado, em vez do trabalho em lotes **Repetição da integração do Dataverse**.

4. Exclua todos os trabalhos em lotes de integração do Dataverse.
   1. Na página **Trabalhos em lotes**, selecione os trabalhos em lotes **Sincronização de solicitação perdida da integração do Dataverse**, **Repetição da integração do Dataverse** e **Sincronização inicial da integração do Dataverse**.
   2. Na faixa de opções de ação, selecione a ação **Alterar status**. 
   3. Selecione **Retenção** e depois selecione **OK**.
   4. Na faixa de opções da ação, selecione a ação **Excluir** e, em seguida, selecione **Sim** para confirmar a ação.

5. Ative os trabalhos em lotes de integração do Dataverse.
   1. Acesse a página **Integração do Microsoft Dataverse** (**Administração do sistema** > **Links** > **Integração** > **Configuração do Dataverse**).
   2. Defina **Habilitar integração do Dataverse** como **Sim**.

6. Vá para a página **Trabalhos em lotes** e confirme se os trabalhos em lotes **Repetição de integração do Dataverse** e **Sincronização de solicitação perdida da integração do Dataverse** foram criados.

Com os trabalhos em lote recriados, você pode monitorar o **Repetição da integração do Dataverse** para verificar a duração da execução do trabalho. Em seguida, você poderá verificar se os registros estão sincronizando corretamente com a solução HCM Common no Microsoft Dataverse.

## <a name="see-also"></a>Consulte também

[Configurar integração do Dataverse](hr-admin-integration-common-data-service.md)<br>
[Redefinir trabalhos em lote presos](hr-admin-troubleshooting-batch-execution.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
