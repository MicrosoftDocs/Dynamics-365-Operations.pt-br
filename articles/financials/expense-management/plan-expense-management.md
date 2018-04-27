---
title: Configurar gerenciamento de despesas
description: "Este artigo descreve as considerações a serem feitas e as decisões a serem tomadas durante o processo de planejamento, antes de configurar o Gerenciamento de despesas no Microsoft Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 08/29/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: GlobalCategory, ProjCategory, TrvLocations, TrvParameters, TrvPaymethod, TrvPerDiems
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 23001
ms.assetid: aa3fd14d-7e94-4603-985f-ca26d6f860ea
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: c87909d9eb3a4d717e0c40289353da0267a51f60
ms.contentlocale: pt-br
ms.lasthandoff: 03/26/2018

---

# <a name="configure-expense-management"></a>Configurar gerenciamento de despesas

[!INCLUDE [banner](../includes/banner.md)]

Este tópico descreve as considerações a serem feitas e as decisões a serem tomadas durante o processo de planejamento, antes de configurar o Gerenciamento de despesas no Microsoft Dynamics 365 for Finance and Operations. No gerenciamento de Despesa, é possível armazenar informações sobre métodos de pagamento, requisições de viagem, relatórios de despesas, políticas etc.

Como muitas das decisões que você toma ao planejar sua configuração do gerenciamento de despesas são baseadas na hierarquia da sua organização e na estrutura financeira, você deve consultar os documentos de planejamento para essas áreas.

## <a name="intercompany-expenses"></a>Despesas intercompanhia

Quando você habilita as despesas intercompanhia, você permite que as entidades legais e os funcionários incorram despesas em nome de outra entidade legal e coletem pagamentos da entidade legal de emprego dentro de sua organização. Por exemplo, um funcionário na entidade legal A conclui um projeto da entidade legal B e o projeto incorrem em despesas de viagem relacionadas. Se as despesas intercompanhia forem habilitadas, o funcionário poderá arquivar um relatório de despesa que lançará a despesa na entidade legal B e a despesa deverá então ser paga pela entidade legal A. Se sua organização não tiver várias entidades legais, você não terá que habilitar as despesas intercompanhias.

**Decisão:** Você deseja habilitar as despesas intercompanhia?

## <a name="financial-management"></a>Gerenciamento financeiro

O gerenciamento de despesas é integrado com o gerenciamento financeiro da sua organização. Muitas das configurações do gerenciamento de despesas serão baseadas nas decisões tomadas sobre as finanças da empresa. As seções a seguir descrevem as várias áreas que exigem o planejamento e as decisões com base nas decisões financeiras da organização e na orientação da equipe de liderança.

### <a name="per-diems"></a>Diárias

Você deve definir as diárias de funcionário que sua organização fornece. Como as diárias normalmente são usadas para cobrir despesas como refeições, hospedagem, e outras despesas extraordinárias, você pode criar regras para as permissões de diária que sua organização oferece. As taxas de diária podem ser baseadas na época do ano, no local de viagem ou em ambos. Quando você define uma regra de diária, você pode especificar que uma porcentagem da taxa de diária será retida se o trabalhador receber refeições ou serviços gratuitos. Você também pode definir as camadas de taxa de diária para definir o número mínimo e máximo de horas que a taxa de diária pode ser aplicada ao deslocamento do funcionário.

**Decisões:**

- As regras de diária padrão para o primeiro e último dia:

    - Qual o número mínimo de horas que um funcionário pode reivindicar para um dia e ainda receber uma diária?
    - Há uma redução no valor que é oferecido para refeições para o primeiro e o último dia? Se houver uma redução, qual é o percentual de redução?
    - Há uma redução no valor que é oferecido para hotel para o primeiro e o último dia? Se houver uma redução, qual é o percentual de redução?
    - Há uma redução no valor que é oferecido para outras despesas incorridas no primeiro e último dia? Se houver uma redução, qual é o percentual de redução?

- Regras padrão de diária:

    - Há uma redução percentual na bonificação de diária para cada refeição se, por exemplo, a refeição for complementar? Se houver uma redução, qual é o percentual de redução para cada refeição?
    - A redução de refeição é calculada por dia, por viagem, ou por número de refeições por dia?
    - Os valores da diária devem ser arredondados de maneira regular ou arredondados?
    - As diárias são calculadas em um período de 24 horas ou em um dia do calendário?

- As regras de diária são baseadas em localização:

    - As taxas de diária variam de acordo com local? Quais locais serão incluídos?
    - Se as taxas de diárias variam de acordo com o local, para cada local, qual valor de porcentagem será fornecido para os seguintes tipos de despesas:

        - Refeições
        - Hotel
        - Outras despesas

### <a name="expense-management-journals-and-accounts"></a>Diários e contas de gerenciamento de despesa

O gerenciamento de despesas exige que você use vários diários e contas. Você deve decidir se, por exemplo, a mesma conta será usada para adiantamentos de dinheiro e contestações de cartão de crédito.

**Decisões:**

- Em qual diário-razão os relatórios de despesas aprovados são lançados?
- Qual conta é utilizada para adiantamentos de dinheiro?
- Os adiantamentos de dinheiro devem ser lançados imediatamente?

### <a name="payment-methods"></a>Meios de pagamento

Ao permitir que os funcionários incorram despesas em nome de sua empresa, você deve definir os métodos de pagamento que os funcionários têm permissão de usar. Por exemplo, você pode permitir que os funcionários usem dinheiro ou um cartão de crédito corporativo. Você também pode permitir que os funcionários usem cartões de crédito pessoais e, em seguida, reembolsá-los. É necessário realizar as seguintes alterações para cada método de pagamento que você permitir.

**Decisões:**

- Quais métodos de pagamento são permitidos?
- Quem é o proprietário das despesas do método de pagamento?
- Há um tipo de contrapartida? Se houver um tipo de contrapartida, que é isso?
- Se houver uma contrapartida, que é a conta?
- Se o método de pagamento for um cartão de crédito, o método de pagamento deverá ser usado somente em transações importadas?

### <a name="expense-categories-and-shared-categories"></a>Categorias de despesa e categorias compartilhadas

Quando os funcionários criam um relatório de despesas, cada despesa que eles registram deve estar associada a uma categoria de despesa. As categorias de despesa são derivadas de categorias compartilhadas que podem ser compartilhadas entre as entidades legais na sua organização. Essas categorias também podem ser compartilhadas no gerenciamento de projetos e na contabilidade do jeito que sua organização está definida. Baseado na definição da organização e na orientação da equipe de implementação, determine se as categorias usadas no gerenciamento de despesas devem serão usadas somente no gerenciamento de despesas ou se devem ser compartilhadas entre o gerenciamento de projetos e na contabilidade e o gerenciamento de despesas. Observe que essas categorias podem ser compartilhadas entre projeto e despesa ou projeto e produção, mas não entre despesa e produção. Você deve realizar as seguintes alterações para cada categoria de despesa.

**Decisões:**

- Qual é a categoria de despesa? Exemplos incluem categorias para voos, hotel ou quilometragem.
- Essa categoria de despesa também pode ser usada no gerenciamento de projeto e contabilidade?
- Qual é o tipo de despesa?
- Qual é o método de pagamento padrão da categoria de despesa?
- As despesas na categoria de despesas devem ser especificadas?
- Qual é a conta padrão principal para a categoria de despesa?
- Qual é o grupo padrão de imposto sobre vendas de item para a categoria de despesa?
- São permitidos métodos de pagamento adicionais para a categoria de despesa? Se os métodos de pagamento adicionais são permitidos, o que são eles?
- Há subcategorias dentro dessa categoria de despesa? Se houver subcategorias, você também deve tomar as seguintes decisões:

    - Algumas das subcategorias são excluídas da restituição de imposto?
    - Qual é o grupo de imposto sobre vendas de item das subcategorias?

Se a categoria de despesa também for usada no gerenciamento de projetos e na contabilidade, responda às perguntas restantes. Caso contrário, vá para a próxima seção.

- Quais contas de custo serão usadas para a seguinte despesa?

    - Custo
    - Alocação de folha de pagamento
    - WIP - Valor de custo
    - Custo de item
    - WIP - Valor de custo - Item
    - Perda acumulada
    - WIP - Perda acumulada

- Quais contas de receita serão usadas para o seguinte?

    - Receita faturada
    - Receita acumulada - valor de venda
    - WIP - Valor de venda
    - Receita acumulada - Produção
    - WIP - Produção
    - Receita acumulada - Lucro
    - WIP - Lucro
    - Receita acumulada - Subscrição
    - WIP - Subscrição

### <a name="taxes"></a>Impostos

Para impostos relacionados a despesas, você deve determinar o que é incluído ou habilitado em relatórios de despesas.

**Decisões:**

- O imposto sobre vendas está incluso nos valores de despesa?
- A restituição de imposto deve ser habilitada nas despesas?

    > [!NOTE]
    > Quando estiver planejando a contabilidade, se optar por aplicar o imposto dos EUA e usar as regras de imposto, você não pode habilitar a restituição de imposto nas despesas. (Para aplicar as regras de imposto e de imposto dos EUA, defina a opção **Aplicar regras de tributação de imposto** como **Sim**.)

## <a name="policies"></a>Políticas

Criando políticas do relatório de despesa, você pode ajudar sua organização a economizar tempo e dinheiro quando os funcionários arcarem com despesas em seu nome. As políticas ajudam a garantir que os funcionários fiquem no orçamento, forneçam todas as informações necessárias e apenas gastem o dinheiro, conforme necessário. Você deve tomar as decisões a seguir para cada política de relatório de despesas e cada política de aprovação de relatório de despesas que você criar.

**Decisões:**

- Qual é o nome da política?
- A que se destina a política de despesa?
- Se você decidiu anteriormente habilitar as despesas intercompanhia, a quais empresas de sua organização essa política se aplica?
- Quando a política entra em vigor?
- Quando a política expira?
- Qual é a regra de política?
- Qual é o resultado da regra de política?

