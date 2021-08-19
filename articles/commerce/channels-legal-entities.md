---
title: Criar entidades legais
description: Este tópico descreve como criar entidades legais no Microsoft Dynamics 365 Commerce, que devem ser criadas e configuradas antes da criação de canais.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: bc5f097a7f941dfa05f4011d9be5caffbb7f01b5f6e67cd7535ef3d1b13f59fe
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740422"
---
# <a name="create-legal-entities"></a>Criar entidades legais

[!include [banner](includes/banner.md)]

Este tópico descreve como criar entidades legais no Microsoft Dynamics 365 Commerce, que devem ser criadas e configuradas antes da criação de canais.

Uma entidade legal é uma organização que tem uma estrutura legal registrada ou legislada. As entidades legais podem participar de contratos legais e são obrigadas a preparar demonstrativos que registram seu desempenho.

Uma empresa é um tipo de entidade legal. Atualmente, empresas são o único tipo de entidade legal que você pode criar, e cada entidade legal está associada a uma ID de empresa. Essa associação existe porque algumas áreas funcionais do programa usam uma ID de empresa, ou *DataAreaID*, nos modelos de dados. Nessas áreas funcionais, as empresas são usadas como um limite para a segurança dos dados. Os usuários podem acessar somente os dados da empresa que estão conectados no momento. 

Ao criar um canal, você deve especificar a qual entidade legal ele pertence.

## <a name="create-a-new-legal-entity"></a>Criar uma nova entidade legal

Para criar uma nova entidade legal no Dynamics 365 Commerce, siga estas etapas.

1. No painel de navegação, Acesse **Módulos \> Configuração da sede \> Entidades legais**.
1. No painel de ação, selecione **Novo**. O painel **Nova entidade legal** é exibido à direita.
1. No campo **Nome**, insira um valor.
1. No campo **Empresa**, insira um valor.
1. No campo **País/região**, insira ou selecione um valor.
1. Selecione **OK**. 

   ![Criação de uma entidade legal.](media/legal-entities.png)

1. Na seção **Geral**, forneça as seguintes informações gerais sobre a entidade legal:: 
   1. Insira um nome de pesquisa, se um nome de pesquisa for necessário. Um nome de pesquisa é um nome alternativo que pode ser usado para procurar essa entidade legal. 
   1. Selecione se a entidade legal está sendo usada como uma empresa de consolidação.
   1. Selecione se essa entidade legal está sendo usada como uma empresa de eliminação. 
   1. Selecione o **idioma padrão** para a entidade. 
   1. Selecione o **fuso horário** para a entidade.
1. Na seção **Endereços**, selecione **Editar** para inserir informações de endereço, como nome da rua e número, CEP e cidade.
1. Na seção **Informações de contato**, insira informações sobre os métodos de comunicação, como endereço de email, URLs e números de telefone.
1. Na seção **Relatório estatutário**, insira os números de registro usados para os relatórios estatutários.
1. Na seção **Números de registro**, insira todas as informações exigidas pela entidade legal.
1. Na seção **Informações de conta bancária**, insira as contas bancárias e os números do banco da entidade legal.
1. Na seção **Comércio exterior e logística**, insira as informações de remessa da entidade legal.
1. Na seção **Sequências numéricas**, é possível exibir as sequências numéricas associadas à entidade legal. Ela estará vazia para começar.
1. Na seção **Imagem no painel**, exiba ou altere a imagem do logotipo e do painel associada à entidade legal.
1. Na seção **Registro de imposto**, insira os números de registro usados nos relatórios para as autoridades fiscais.
1. Na seção **Imposto 1099**, insira a informação 1099 da entidade legal.
1. Na seção **Informações sobre impostos**, insira as informações fiscais da entidade legal.
1. Selecione **Salvar**.

A imagem a seguir mostra detalhes de um exemplo de entidade legal.

![Seção Geral da entidade legal.](media/legal-entities-general.png)
   
## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de organizações e hierarquias organizacionais](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[Planejar sua hierarquia da organização](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[Hierarquias da organização](channels-org-hierarchies.md)

[Visão geral de canais](channels-overview.md)

[Pré-requisitos de configuração de canal](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
