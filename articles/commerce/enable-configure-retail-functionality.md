---
title: Inicializar dados de propagação em novos ambientes do Commerce
description: Este artigo descreve os dados que são criados como parte do processo de inicialização do Dynamics 365 Commerce.
author: josaw1
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 49621
ms.assetid: 4dc762eb-190e-4485-8f55-b0cafc81bc37
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 14d56636b48d8f8ff15863bb04c762e398f8c370664fbd52f80ed5f05f0e4895
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6718722"
---
# <a name="initialize-seed-data-in-new-commerce-environments"></a>Inicializar dados de propagação em novos ambientes do Commerce

[!include [banner](includes/banner.md)]

Este artigo descreve os dados que são criados como parte do processo de inicialização do Dynamics 365 Commerce.

Depois que a solução Commerce tiver sido implantada por meio do Microsoft Dynamics Lifecycle Services (LCS), você deverá inicializar a configuração de Commerce para criar os dados básicos de configuração.

> [!IMPORTANT]
> Antes de inicializar a configuração do Commerce, verifique se você especificou um idioma e um endereço postal para cada entidade legal em que vai configurar repositórios. Essa etapa deve ser concluída para cada entidade legal usada para comércio.

Para inicializar a configuração, siga estas etapas.

1. Inicie o cliente do Commerce.
2. Clique em **Retail e Commerce** &gt; **Configuração da sede** &gt; **Parâmetros** &gt; **Parâmetros do Commerce**.
3. Clique em **Inicializar**.

A inicialização cria os seguintes dados de configuração padrão:

- Trabalhos e subtrabalhos do agendador do Commerce
- Esquema de canal de comércio
- Agendas de distribuição do Commerce
- Layouts de tela padrão, que inclui grades de botões, imagens e temas
- Informações sobre fuso horário
- Operações de PDV (ponto de venda)
- Permissões do PDV
- Relatórios do canal
- Metadados de atributo
- Modelos de validação de entidade
- Trabalho em lotes para limpar o histórico da sessão do Commerce Data Exchange

Além disso, os registros relacionados à PCI (indústria de pagamento por cartão) estão habilitados para o banco de dados do Commerce.

> [!NOTE]
> Há uma opção para configurar separadamente o agendador do Commerce. Essa opção permite redefinir a configuração do agendador do Commerce para suas configurações padrão.

Depois que a inicialização for concluída, você deverá configurar os dados adicionais do Commerce. Eis alguns exemplos:

- Parâmetros de comércio
- Parâmetros do agendador do Commerce
- Canais do Commerce
- Registros e dispositivos
- Sortimentos


[!INCLUDE[footer-include](../includes/footer-banner.md)]