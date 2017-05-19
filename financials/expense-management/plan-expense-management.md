---
title: Configurar gerenciamento de despesas
description: "Este artigo descreve as considerações e as alterações que você deve fazer durante o processo de planejamento, antes de configurar o gerenciamento de Despesa no Microsoft Dynamics AX. Na área de gerenciamento de despesas, é possível armazenar informações sobre métodos de pagamento, requisições de viagem, relatórios de despesas, as diretivas, dentre outras coisas."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: GlobalCategory, ProjCategory, TrvLocations, TrvParameters, TrvPaymethod, TrvPerDiems
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 23001
ms.assetid: aa3fd14d-7e94-4603-985f-ca26d6f860ea
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 447ba56a279a29392b00119730c3594fa4ea80f6
ms.contentlocale: pt-br
ms.lasthandoff: 04/25/2017


---

# <a name="configure-expense-management"></a>Configurar gerenciamento de despesas

[!include[banner](../includes/banner.md)]


Este artigo descreve as considerações e as alterações que você deve fazer durante o processo de planejamento, antes de configurar o gerenciamento de Despesa no Microsoft Dynamics AX. Na área de gerenciamento de despesas, é possível armazenar informações sobre métodos de pagamento, requisições de viagem, relatórios de despesas, as diretivas, dentre outras coisas. 

Como muitas das decisões que você toma ao planejar sua configuração do gerenciamento de despesas são baseadas na hierarquia da sua organização e na estrutura financeira, você deve consultar os documentos de planejamento para essas áreas.

## <a name="intercompany-expenses"></a>Despesas intercompanhia
Quando você habilita as despesas intercompanhia, você permite que as entidades legais e os funcionários incorram despesas e coletem pagamentos de outra entidade legal dentro de sua organização. Por exemplo, um funcionário na entidade legal A conclui um projeto para a entidade legal B. Se as despesas intercompanhia estiverem habilitadas, o funcionário poderá arquivar uma folha de ponto e ser pago pela entidade legal B. Se sua organização não possui diversas entidades legais, você não precisará habilitar as despesas intercompanhia. **Decisão:** Você deseja habilitar as despesas intercompanhia?

## <a name="financial-management"></a>Gerenciamento financeiro
O gerenciamento de despesas é integrado com o gerenciamento financeiro da sua organização. Muitas das configurações do gerenciamento de despesas serão baseadas nas alterações que você fez sobre as finanças da empresa. As seções a seguir descrevem as áreas diferentes que exigem o planejamento e as decisões com base nas decisões financeiras da organização e na orientação da equipe de liderança.

### <a name="per-diems"></a>Diárias

Você deve definir as diárias de funcionário que sua organização fornece. Como as diárias normalmente são usadas para cobrir despesas como refeições, hospedagem, e outras despesas extraordinárias, você pode criar regras para as permissões de diária que sua organização oferece. As taxas de diária podem ser definidas com base na época do ano, o local de viagem ou ambos. Quando você define uma regra de diária, você pode especificar que uma porcentagem da taxa de diária será retida se o trabalhador receber refeições ou serviços gratuitos. Você também pode definir as camadas de taxa de diária para definir o número mínimo e máximo de horas que a taxa de diária pode ser aplicada ao deslocamento do funcionário. **Decisões:**

-   As regras de diária padrão para o primeiro e último dia:
    -   Qual o número mínimo de horas que um funcionário pode reivindicar para um dia e ainda receber uma diária?
    -   Há uma redução no valor que é oferecido para refeições para o primeiro e o último dia? Se sim, qual o percentual da redução?
    -   Há uma redução no valor que é oferecido para hotel para o primeiro e o último dia? Se sim, qual o percentual da redução?
    -   Há uma redução no valor que é oferecido para outras despesas incorridas no primeiro e último dia? Se sim, qual o percentual da redução?
-   Regras padrão de diária:
    -   Há uma redução percentual na bonificação de diária para cada refeição se, por exemplo, a refeição for complementar? Se sim, qual a porcentagem de redução para cada refeição?
    -   A redução de refeição é calculada por dia, por viagem, ou por número de refeições por dia?
    -   Os valores de diária deve ser arredondados de forma comum ou para cima?
    -   As diárias são calculadas em um período de 24 horas ou em um dia do calendário?
-   Regras de diária baseadas em localização:
    -   As taxas de diária variam com base na localização e quais locais estão inclusos?
    -   Se a taxa de diária varia de acordo com o local, para cada local, o valor da porcentagem é fornecido para:
        -   refeições
        -   hotel
        -   outras Despesas

### <a name="expense-management-journals-and-accounts"></a>Diários e contas de gerenciamento de despesa

O gerenciamento de despesas exige que você use vários diários e contas. Você deve decidir se, por exemplo, a mesma conta será usada para adiantamentos de dinheiro e contestações de cartão de crédito. **Decisões:**

-   Em qual diário-razão os relatórios de despesas aprovados são lançados?
-   Qual conta é utilizada para adiantamentos de dinheiro?
-   Os adiantamentos de dinheiro devem ser lançados imediatamente?

### <a name="payment-methods"></a>Meios de pagamento

Ao permitir que os funcionários incorram despesas em nome de sua empresa, você deve definir os métodos de pagamento que os funcionários têm permissão de usar. Por exemplo, você pode permitir que os funcionários usem dinheiro ou um cartão de crédito corporativo. Você também pode permitir que os funcionários usem cartões de crédito pessoais e, em seguida, reembolsá-los. É necessário realizar as seguintes alterações para cada método de pagamento que você permitir. **Decisões:**

-   Quais métodos de pagamento são permitidos?
-   Quem é o proprietário das despesas do método de pagamento?
-   Há um tipo de contrapartida? Se sim, qual é ele?
-   Se houver uma contrapartida, que é a conta?
-   Se o método de pagamento for um cartão de crédito, o método de pagamento deverá ser usado somente em transações importadas?

### <a name="expense-categories-and-shared-categories"></a>Categorias de despesa e categorias compartilhadas

Quando os funcionários criam um relatório de despesas, cada despesa que eles registram deve estar associada a uma categoria de despesa. As categorias de despesa são derivadas de categorias compartilhadas que podem ser compartilhadas entre as entidades legais na sua organização. Essas categorias também podem ser compartilhadas no gerenciamento de projetos e na contabilidade, dependendo de como sua organização está definida. Baseado na definição da organização e na orientação da equipe de implementação, determine se as categorias usadas no gerenciamento de despesas devem ser usadas somente em despesa ou se devem ser compartilhadas entre projeto e despesa. Observe que essas categorias podem ser compartilhadas entre projeto e despesa ou projeto e produção, mas não entre despesa e produção. Você deve realizar as seguintes alterações para cada categoria de despesa. **Decisões:**

-   Qual é a categoria de despesa? Por exemplo, voos, hotel, ou quilometragem.
-   Essa categoria de despesa também pode ser usada no gerenciamento de projeto e contabilidade?
-   Qual é o tipo de despesa?
-   Qual é o método de pagamento padrão da categoria de despesa?
-   As despesas nesta categoria precisam ser especificadas?
-   Qual é a conta padrão principal para a categoria de despesa?
-   Qual é o grupo padrão de imposto sobre vendas de item para a categoria de despesa?
-   São permitidos métodos de pagamento adicionais para a categoria de despesa? Se sim, quais são eles?
-   Há subcategorias dentro dessa categoria de despesa? Se sim:
    -   Algumas das subcategorias são excluídas da restituição de imposto?
    -   Qual é o grupo de imposto sobre vendas de item das subcategorias?

    Se esta categoria de despesa também for usada no gerenciamento de projetos e na contabilidade, responda às perguntas restantes. Caso contrário, você concluirá nesta seção.
-   Quais contas de custo serão usadas para o seguinte?
    -   Custo
    -   Alocação de folha de pagamento
    -   WIP - Valor de custo
    -   Custo de item
    -   WIP - Valor de custo - Item
    -   Perda acumulada
    -   WIP - Perda acumulada
-   Quais contas de receita serão usadas para o seguinte?
    -   Receita faturada
    -   Receita acumulada - valor de venda
    -   WIP - Valor de venda
    -   Receita acumulada - Produção
    -   WIP - Produção
    -   Receita acumulada - Lucro
    -   WIP - Lucro
    -   Receita acumulada - Subscrição
    -   WIP - Subscrição

 

### <a name="taxes"></a>Impostos

Para impostos relacionados a despesas, você deve determinar o que é incluído ou habilitado em relatórios de despesas. **Decisões:**

-   O imposto sobre vendas está incluso nos valores de despesa?
-   A restituição de imposto deve ser habilitada nas despesas?

Observe que se durante o planejamento da contabilidade, você decidiu aplicar os impostos sobre vendas e as regras de imposto sobre o uso dos EUA, que é feito alternando o campo **Aplicar regras de tributação de imposto** para Sim, não será possível habilitar a restituição de imposto nas despesas.

## <a name="policies"></a>Políticas
Você pode criar políticas de relatório de despesas de modo que sua organização possa poupar tempo e dinheiro quando os funcionários incorrerem em despesas em seu nome. As políticas garantem que os funcionários fiquem dentro do orçamento, forneçam todas as informações necessárias e gastem o dinheiro somente conforme necessário. Você deve tomar as decisões a seguir para cada política de relatório de despesas e cada política de aprovação de relatório de despesas que você criar. **Decisões:**

-   Qual é o nome da política?
-   A que se destina a política de despesa?
-   Se você decidiu anteriormente habilitar as despesas intercompanhia, a quais empresas em sua organização essa política se aplica?
-   Quando a política entra em vigor?
-   Quando a política expira?
-   Qual é a regra de política?
-   Qual é o resultado da regra de política?





