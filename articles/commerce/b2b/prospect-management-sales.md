---
title: Gerenciar usuários parceiros comerciais em sites de comércio eletrônico B2B usando o Dynamics 365 Sales
description: Este artigo descreve como usar o Microsoft Dynamics 365 Sales para gerenciar as aprovações de parceiros comerciais para os sites de venda entre empresas (B2B) do Dynamics 365 Commerce.
author: shajain
ms.date: 2/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: ac4aa15f2c6e7f557105254c2c8ce743a9466985
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878612"
---
# <a name="manage-business-partner-users-on-b2b-e-commerce-websites-using-dynamics-365-sales"></a>Gerenciar usuários parceiros comerciais em sites de comércio eletrônico B2B usando o Dynamics 365 Sales

[!include [banner](../../includes/banner.md)]

Este artigo descreve como usar o Microsoft Dynamics 365 Sales para gerenciar as aprovações de parceiros comerciais para os sites de venda entre empresas (B2B) do Dynamics 365 Commerce. As organizações que já investiram na solução do Dynamics 365 Sales podem usar seus conceitos de cliente potencial e de oportunidade para o processo de aprovação de parceiros de comércio eletrônico B2B.

Para obter informações detalhadas sobre o processo de aprovação de parceiro comercial B2B, consulte [Gerenciar usuários de parceiros comerciais em sites de comércio eletrônico B2B](manage-b2b-users.md).

Parceiros comerciais potenciais podem iniciar o processo de integração para um site de comércio eletrônico B2B enviando uma solicitação de integração por meio de um link no site B2B. Depois que a solicitação é enviada e os trabalhos relevantes (como **P-0001** e **Sincronizar solicitações de ordens e canais**) são executados no Commerce headquarters, a solicitação de integração é salva na página **Todos os clientes potenciais** do Commerce headquarters. O processo de aprovação do parceiro comercial pode ser concluído no Sales.

Depois que a integração entre o Sales e o Commerce for habilitada, a criação de um parceiro comercial potencial no Commerce provocará a geração de um *cliente potencial* no Sales.

A ilustração a seguir mostra um exemplo de uma página de criação de cliente potencial para um parceiro comercial potencial no Sales.

![Página de criação de cliente potencial no Dynamics 365 Sales.](../media/LeadInSales.png)

Na ilustração, a seção **Contato** mostra a pessoa que enviou a solicitação de integração e a seção **Empresa** mostra a organização. Uma observação na seção **Linha do tempo** indica que o cliente potencial foi gerado pela infraestrutura de gravação dupla. Como ele foi criado pela infraestrutura de gravação dupla, esse cliente potencial não aparecerá na lista suspensa **Meus clientes potenciais em aberto**. Em vez disso, aparecerá em uma nova exibição chamada **Todos os clientes potenciais B2B**.

Por meio do processo de qualificação de cliente potencial padrão no Sales, quando um usuário "qualifica" o cliente potencial, um registro de *oportunidade*, um registro de *contato* e um registro de *conta* são criados. A infraestrutura de gravação dupla é usada para gravar os registros de contato e de conta para o Commerce. O contato é criado como um cliente do tipo *pessoa* e a empresa é criada como um cliente do tipo *organização*. Se um usuário selecionar **Fechar como ganha** para a oportunidade, o cliente potencial será aprovado no Commerce. A aprovação de um cliente potencial faz com que uma hierarquia de cliente seja criada.

Todos os processos de negócios restantes ocorrem no Commerce. Esses processos incluem enviar email para o parceiro comercial, definir o gerenciamento de limite de crédito para os usuários e adicionar mais usuários ao site B2B. No entanto, se um usuário desqualificar o cliente potencial ou marcar a oportunidade como perdida em vez de qualificar o cliente potencial, o cliente potencial no Commerce será marcado como recusado e um email de recusa será enviado ao solicitante.

## <a name="enable-integration-between-sales-and-commerce"></a>Habilitar integração entre o Sales e o Commerce

A integração entre o Sales e o Commerce depende da infraestrutura de gravação dupla. Portanto, a gravação dupla deve ser habilitada e estar funcionando para que os clientes criados em um sistema sejam gravados no outro sistema. Para obter mais informações sobre a infraestrutura de gravação dupla, consulte [Visão geral da gravação dupla](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview).

Depois que a configuração de gravação dupla tiver sido concluída, o parceiro de implementação poderá acessar o [Microsoft AppSource](https://appsource.microsoft.com/) e procurar a solução de nome [Soluções de gravação dupla do Commerce](https://partner.microsoft.com/dashboard/commercial-marketplace/offers/7ca1d8c9-dc79-4cb7-a82e-8dc96a25acca/overview). Instale o pacote usando o assistente de instalação padrão e, em seguida, teste-o criando um cliente potencial em um site B2B. Depois que o cliente potencial for criado, verifique se a solicitação mostrada em **Todos os clientes potenciais** aparece no Commerce e verifique se o cliente potencial é mostrado como tal no Sales.

## <a name="additional-resources"></a>Recursos adicionais

[Gerenciar usuários parceiros comerciais em sites de comércio eletrônico B2B](manage-b2b-users.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
