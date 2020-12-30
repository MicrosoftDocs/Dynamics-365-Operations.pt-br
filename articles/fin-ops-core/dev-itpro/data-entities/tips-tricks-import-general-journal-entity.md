---
title: Práticas recomendadas para importar vouchers usando a entidade Diário geral
description: Este tópico fornece dicas para importar dados para o diário geral usando Entidade de diário geral.
author: rcarlson
manager: AnnBe
ms.date: 04/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 94363
ms.assetid: 0b8149b5-32c5-4518-9ebd-09c9fd7f4cfc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f5b36e11bd9ef338334f7ac1b6412edb7754010f
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687634"
---
# <a name="best-practices-for-importing-vouchers-by-using-the-general-journal-entity"></a>Práticas recomendadas para importar vouchers usando a entidade Diário geral

[!include [banner](../includes/banner.md)]

Este tópico fornece dicas para importar dados para o diário geral usando Entidade de diário geral.

Você pode usar a entidade de diário geral para importar somente os comprovantes que têm um tipo de conta ou contrapartida de **Razão**, **Cliente**, **Fornecedor** ou **Banco**. O voucher pode ser digitado como uma linha, usando o campo **Conta** e o campo **Contrapartida**, ou como um comprovante de várias linhas, onde somente o campo **Conta** é usado (e **Contrapartida** é deixado em branco em cada linha). A entidade do diário geral não suporta cada tipo de conta. Em vez disso, existem outras entidades para cenários onde diferentes combinações de tipos de conta são necessárias. Por exemplo, para importar uma transação de projeto, use a entidade do diário de despesas do projeto. Cada entidade foi projetada para oferecer suporte a cenários específicos. Isso significa que campos adicionais podem estar disponíveis nas entidades para esses cenários. Contudo, campos adicionais podem não estar disponíveis em entidades para diferentes cenários.

## <a name="setup"></a>Instalação
Antes de você importar usando a entidade diário geral, valide a configuração a seguir:

- **Configuração de sequência numérica para o número de lote do diário** — por padrão, quando você importar usando a entidade diário geral, os usos de número de lote do diário na sequência numérica que são definidas nos parâmetros da contabilidade. Se você definir a sequência numérica para o número do diário para **Manual**, um número de padrão não é aplicado. Essa configuração não é suportada.
- **Configuração da dimensão financeira** – cada organização deve definir a ordem de dimensões financeiras quando entidades são usadas para importar as transações. A ordem é definida para o formato **Integração de dimensões contábeis**, em **Contabilidade** &gt; **Plano de contas** &gt; **Dimensões** &gt; **Configuração da dimensão financeira para aplicações de integração** &gt; **Selecionar entidades de dados**. Os segmentos da conta contábil que são importados devem ter a mesma ordem. Caso contrário, ocorrerá um erro durante a importação.

## <a name="general-journal-entity-setup"></a>Configuração de entidade de diário geral
Duas configurações em Gerenciamento de dados afetam como o número de lote de diário padrão ou o número de voucher é aplicado:

- **Processamento baseado conjunto** (na entidade de dados)
- **Gerado automaticamente** (no mapeamento de campo)

As seções a seguir descrevem o efeito dessas configurações. Elas também explicam como o sistema gera números de lote para diários e números de comprovante.

### <a name="journal-batch-number"></a>Número do lote do diário

- A configuração **processamento baseado em conjunto** na entidade diário geral não afeta a maneira que os números de lote do diário são gerados.
- Se o campo **Número de lote do diário** é definido como **Gerado automaticamente**, um novo número de lote do diário é criado para cada linha que é importada. Este comportamento não é recomendado. A configuração **Gerado automaticamente** é encontrada no projeto de importação, em **Exibir mapa** diante da guia **Detalhes de mapeamento**.
- Se o campo **Número de lote do diário** não é definido como **Gerado automaticamente**, o número de lote do diário é criado como segue:

    - Se o número de lote do diário que é definido no arquivo importado corresponder a um diário diário existente não lançado, todas as linhas que possuem um número de lote do diário correspondentes são importadas para o diário existente. As linhas nunca são importadas em um número de lote de jornal lançado. Em vez disso, um novo número é criado.
    - Se o número de lote do diário que é definido no arquivo importado não corresponder a um diário diário existente não lançado, todas as linhas que possuem um número de lote do diário correspondentes são importadas para um novo diário existente. Por exemplo, todas as linhas que possuem um número de lote do diário 1 são importadas para um novo diário, e todas as linhas que possuem um número de lote do diário 2 são importadas para um novo diário de segundo. O número de lote do diário é criado usando a sequência numérica que é definida nos parâmetros da contabilidade.

### <a name="voucher-number"></a>Número do comprovante

- Quando você usa a configuração **Processamento baseado em conjunto** na entidade Diário geral, o número do comprovante deve ser fornecido no arquivo importado. Todas as transações no diário geral são atribuída ao número do comprovante que é fornecido no arquivo importado, mesmo se o comprovante não for balanceado. Observe os pontos a seguir se você deseja usar o processamento baseado em conjunto, mas você também deseja usar a sequência numérica que é definida para números de comprovante.

    - Para habilitar essa funcionalidade, no nome do diário usado para importações, defina **Alocação de número no lançamento** para **Sim**.
    - Um número de comprovante ainda deve ser definido no arquivo importado. No entanto, esse número é temporário e será substituído pelo número do comprovante quando o diário é lançado. Certifique-se de que as linhas do diário são agrupadas corretamente por número de comprovante temporário. Por exemplo, durante a postagem, é constatado que três linhas possuem um voucher temporário. O número de voucher temporário de todas as três linhas é substituído pelo número seguinte na sequência de números. Se essas três linhas não são uma entrada equilibrada, o comprovante não será publicado. Em seguida, se linhas forem encontradas que possuem um número de comprovante temporário 2, esse número será substituído pelo próximo número de comprovante na sequência e assim por diante.

- Se você não usar a configuração **Processamento baseado em conjunto**, não é necessário fornecer um número de voucher no arquivo importado. Os números de comprovante são criados durante a importação, com base na configuração do nome do diário (**Um comprovante só**, **Na conexão do saldo**, e assim por diante). Por exemplo, se o nome de diário é definido como **Na conexão do saldo**, a primeira linha recebe um novo número de comprovante padrão. Em seguida, o sistema avalia a linha para determinar se os débitos são iguais aos créditos. Se existir uma contrapartida na linha, a próxima linha importada recebe um novo número de comprovante. Se nenhuma contrapartida existir, o sistema avalia se os débitos são iguais aos créditos que cada nova linha é importada.
- Se o campo **Número do comprovante** é definido como **Gerado automaticamente**, a importação não tem êxito. A configuração **Gerado automaticamente** para o campo **Número do comprovante** não é suportado.

Por padrão, a entidade de diário geral usa processamento baseado em conjunto. Depois de avaliar os requisitos de negócios para sua organização, você pode alterar a configuração **Processamento baseado em conjunto** clicando em **Entidades de dados** no espaço de trabalho **Gerenciamento de dados**. Processamento baseado em conjunto é usado para acelerar o processo de importação. Se você não usar o processamento baseado em conjunto, a importação da importação de entidade diário geral será mais lenta.
