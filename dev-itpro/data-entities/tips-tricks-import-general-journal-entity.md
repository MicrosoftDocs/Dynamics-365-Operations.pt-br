---
title: "Práticas recomendadas para importar comprovantes usando a entidade de diário geral"
description: "Este tópico fornece dicas para importar dados no diário geral com a entidade do diário geral."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 94363
ms.assetid: 0b8149b5-32c5-4518-9ebd-09c9fd7f4cfc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 81a52acd1d9baa12fcfe9d848441901894fa5682
ms.lasthandoff: 03/31/2017


---

# <a name="best-practices-for-importing-vouchers-using-the-general-journal-entity"></a>Práticas recomendadas para importar comprovantes usando a entidade de diário geral

Este tópico fornece dicas para importar dados no diário geral com a entidade do diário geral.  

Você pode usar a entidade do diário geral para importar comprovantes de com um tipo da conta ou de compensação ** motivo, cliente, fornecedor, ou banco. ** O comprovante pode ser inserida como uma linha, usando ambos ** conta ** o campo e ** contrapartida ** campo, ou como uma combinado comprovante, no qual apenas ** conta ** o campo é usado (e ** contrapartida ** ficar em branco em cada linha.) A entidade do diário geral não suporta cada tipo de conta. Em vez disso, existem outras entidades para cenários onde diferentes combinações de tipos de conta são necessárias. Por exemplo, para importar uma transação de projetos, use a entidade do diário de despesas do projeto. Cada entidade é criado para dar suporte os cenários específicos, se os campos adicionais da mídia podem estar disponíveis em entidades para estes cenários mas não em entidades para um cenário diferente.

## <a name="setup"></a>Instalação
Antes de importar usando a entidade do diário geral, confirme instalação do seguinte:

-   ** Numerar a configuração de sequência para o número de lote do diário ** - por padrão, quando você importa usando a entidade do diário geral, o número de diário de lote usa a sequência numérica definida em parâmetros de contabilidade. Se você definir a sequência numérica para o número do diário para **Manual**, um número de padrão não é aplicado. Essa configuração não é suportada.
-   ** A configuração da dimensão financeira ** - cada organização deve definir a ordem de dimensões financeiras às entidades são usadas para transações de importação. A ordem está definido para ** integração dimensões contábeis ** o formato, ** contabilidade ** &gt; ** no gráfico de contas ** &gt; ** dimensões ** &gt; ** configuração de dimensão financeira para aplicativos de integração ** &gt; ** entidades de dados selecionadas **. Os segmentos da conta contábil que são importados devem ter a mesma ordem. Caso contrário, ocorrerá um erro durante a importação.

## <a name="general-journal-entity-setup"></a>Configuração de entidade de diário geral
Duas configurações em gerenciamento de dados como afetam o número de lote do diário padrão ou o número do comprovante são aplicadas:

-   ** processamento Definir- ** (baseado na entidade de dados)
-   ** ** sido gerada automaticamente (em mapeamento de)

As seções a seguir descrevem o efeito dessas configurações e também explicam como os números de lote do diário e os números de comprovantes são gerados.

### <a name="journal-batch-number"></a>Número do lote do diário

-   A configuração **processamento baseado em conjunto** na entidade diário geral não afeta a maneira que os números de lote do diário são gerados.
-   Se o campo **Número de lote do diário** é definido como **Gerado automaticamente**, um novo número de lote do diário é criado para cada linha que é importada. Este comportamento não é recomendado. A configuração **Gerado automaticamente** é encontrada no projeto de importação, em **Exibir mapa** diante da guia **Detalhes de mapeamento**.
-   Se o campo **Número de lote do diário** não é definido como **Gerado automaticamente**, o número de lote do diário é criado como segue:
    -   Se o número de lote do diário que está definido no arquivo importado corresponde uma existente, o diário não lançada no Microsoft Dynamics 365 para operações, todas as linhas que possuem um número de lote do diário serão importadas em diário existente. As linhas nunca são importadas em um número de lote de jornal lançado. Em vez disso, um novo número é criado.
    -   Se o número de lote do diário que está definido no arquivo importado não corresponde uma existente, o diário não lançada em dynamics 365 para operações, todas as linhas com o mesmo número de lote do diário serão agrupadas em um novo diário. Por exemplo, todas as linhas que possuem um número de lote do diário 1 são importadas para um novo diário, e todas as linhas que possuem um número de lote do diário 2 são importadas para um novo diário de segundo. O número de lote do diário é criado usando a sequência numérica que é definida nos parâmetros da contabilidade.

### <a name="voucher-number"></a>Número do comprovante

-   Quando você usa a configuração **Processamento baseado em conjunto** na entidade Diário geral, o número do comprovante deve ser fornecido no arquivo importado. Todas as transações no diário geral são atribuída ao número do comprovante que é fornecido no arquivo importado, mesmo se o comprovante não for balanceado. Se quiser usar processamento definir- baseia, mas também deseja usar a sequência numérica definida para números de comprovante em dynamics 365 para operações, um hotfix foi fornecida para a versão fevereiro de 2016. O número do hotfix é 3170316 e está disponível para download a partir do ciclo de vida dos serviços (LCS). Para obter mais informações, consulte [Baixar hotfixes dos serviços de ciclo de vida](..\migration-upgrade\download-hotfix-lcs.md).
    -   Para habilitar essa funcionalidade, o nome de diário usado para importações em dynamics 365 para operações, definido ** numerar a alocação na postagem ** ** Sim **.
    -   Um número de comprovante ainda deve ser definido no arquivo importado. Porém, esse número é temporário e for substituído por dynamics 365 para o número de comprovante de operações quando o diário for lançado. Você deve certificar-se de que as linhas do diário são agrupadas corretamente por número de comprovante temporário. Por exemplo, durante a postagem, três linhas são localizadas que têm um número temporário de comprovante. de 1. O número temporário de comprovante das três linhas for substituído pelo próximo número na sequência numérica. Se essas três linhas não são uma entrada equilibrada, o comprovante não foi publicado. Em seguida, se linhas forem encontradas que possuem um número de comprovante temporário 2, esse número será substituído pelo próximo número de comprovante na sequência numérica e assim por diante.

<!-- -->

-   Quando você não usa ** processamento Definir- baseado ** a configuração, você não precisa fornecer um número de comprovante no arquivo importado. Os números de comprovante são criados durante a importação, com base na configuração do nome do diário (**Um comprovante só**, **Na conexão do saldo**, e assim por diante). Por exemplo, se o nome de diário é definido como **Na conexão do saldo**, a primeira linha recebe um novo número de comprovante padrão. Em seguida, o sistema avalia a linha para determinar se os débitos são iguais aos créditos. Se existir uma contrapartida na linha, a próxima linha importada recebe um novo número de comprovante. Se nenhuma contrapartida existir, o sistema avalia se os débitos são iguais aos créditos que cada nova linha é importada.
-   Se o campo **Número do comprovante** é definido como **Gerado automaticamente**, a importação não tem êxito. A configuração **Gerado automaticamente** para o campo **Número do comprovante** não é suportado.

Por padrão, a entidade de diário geral usa processamento baseado em conjunto. Depois de avaliar os requisitos de negócios para sua organização, você pode alterar a configuração **Processamento baseado em conjunto** clicando em **Entidades de dados** no espaço de trabalho **Gerenciamento de dados**. Processamento baseado em conjunto é usado para acelerar o processo de importação. Se você não usar o processamento baseado em conjunto, a importação da importação de entidade diário geral será mais lenta.


