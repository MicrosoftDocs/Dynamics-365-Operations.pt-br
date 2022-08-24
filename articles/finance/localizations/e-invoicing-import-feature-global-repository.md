---
title: Importar recursos do Repositório global
description: Este artigo explica como importar recursos de globalização do repositório global.
author: gionoder
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 5a72673e17c5653d43b60d3348d5518e09c40a15
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278301"
---
# <a name="import-features-from-the-global-repository"></a>Importar recursos do Repositório global

[!include [banner](../includes/banner.md)]

O repositório global contém recursos de faturamento eletrônico compartilhados com o seu provedor de configuração. Todos os recursos de faturamento eletrônico fornecidos pela Microsoft são compartilhados com todas as empresas. Você terá acesso automaticamente a todos os recursos de faturamento eletrônico que a Microsoft lança e publica no repositório global.

Para começar a trabalhar com recursos de faturamento eletrônico compartilhados com seu provedor de configuração, importe-os para a instância do RCS (Regulatory Configuration Service) do repositório global. Em seguida, revise os detalhes do recurso, como as configurações de relatório eletrônico (ER) e as tubulações de processamento.

## <a name="import-a-feature-from-the-global-repository"></a>Importar um recurso do Repositório global

1. Entre em sua conta do RCS.
2. No espaço de trabalho **Recurso de globalização** na seção **Recursos**, selecione o bloco **Faturamento eletrônico**.
3. Selecione **Importar** para abrir a pesquisa **Importar recurso do Repositório global**.
4. Para procurar os recursos de faturamento eletrônico disponíveis no repositório global para um provedor de configuração específico, sincronize a instância RCS da sua organização selecionando **Sincronizar**. Depois que a sincronização é concluída, a lista de recursos de faturamento eletrônico disponíveis é atualizada a partir do repositório global. Essa atualização pode levar alguns minutos.
5. Selecione o recurso a ser importado e, em seguida, selecione **Importar**.

Para visualizar o recurso de faturamento eletrônico importado, verifique se o provedor de configuração correto está selecionado. Por padrão, os recursos que foram criados pelo provedor de configuração ativa são automaticamente filtrados. Você pode ajustar o filtro para exibir recursos que foram criados por outros fornecedores, como o provedor de configuração da Microsoft.

Agora você pode trabalhar com o recurso importado. Você pode revisar os detalhes e criar um novo recurso usando o recurso importado como um modelo.

> [!NOTE]
> Você pode modificar um recurso somente se ele tiver sido criado pelo provedor de configuração que está ativo no momento. Você pode criar um novo recurso usando o recurso original como base. Em seguida, você poderá fazer as alterações necessárias ou configurar os parâmetros.

Quando a Microsoft ou outra empresa que compartilha recursos de globalização com os recursos de atualização de sua empresa tiver sido importado, você poderá verificar versões atualizadas, selecionando **Verificar se há atualizações de recursos** na seção **Configurações relacionadas** do espaço de trabalho **Recursos de globalização**.

Se você perceber que há atualizações para um recurso usado como modelo, poderá importar uma nova versão depois de sincronizar a lista de recursos publicados no repositório global.
