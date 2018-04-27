---
title: "Parâmetros de gerenciamento de despesas"
description: "Os parâmetros a seguir controlam o comportamento no Gerenciamento de despesas."
author: KimANelson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TrvParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 22f766b780d10d4fc615660990729f008007787a
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="expense-management-parameters"></a>Parâmetros de gerenciamento de despesas

[!INCLUDE [banner](../includes/banner.md)]

-----------------------------

Os parâmetros controlam o comportamento geral no Gerenciamento de despesas.

### <a name="general"></a>Geral

| **Campo**                                                | **Descrição**                                                 |
|----------------------------------------------------------|---------------------------------------------------------------------|
| **Taxa padrão de quilometragem**                             | Insira a taxa de reembolso para despesas de quilometragem. A taxa será multiplicada pela quilometragem inserida nas despesas para calcular o valor reembolsado da despesa de viagem.                       |
|**Despesas pessoais pagas por**                             | Selecione o responsável por pagar todos os valores de transação de cartão de crédito categorizados como pessoais.                                                                                                     |
|**Exibir o relatório de despesas inteiro em drillback**               | Selecione essa opção para exibir todas as despesas para um relatório de despesas ao exibir os detalhes do documento original de um comprovante específico gerado quando o relatório de despesas foi lançado.              |
|**A pré-autorização da viagem é obrigatória**                 | Selecione essa opção para exigir que uma requisição de viagem seja enviada e aprovada antes que um funcionário possa enviar um relatório de despesas.                                                                    |
|**Permitir a edição de distribuições antes do lançamento**            | Selecione se as distribuições de um relatório de despesas podem ser editadas antes da postagem.                                                                                                                 |
|**Avaliar as políticas de gerenciamento de despesas**                     | Selecione quando as despesas serão avaliadas para determinar se um política de despesas foi violada. As despesas podem ser verificadas quanto às violações quando a entrada de despesa é inserida e salva ou quando a despesa é enviada para aprovação. As regras de política para recebimentos necessários serão verificadas quando a linha de despesa for salva.                   |
|**Permitir linhas de despesa intercompanhia**                         | Selecione se será permitida a entrada de despesas para outras entidades legais em um relatório de despesas.                                                                                                          |
|**Permitir a edição da taxa de câmbio para despesas de cartão de crédito** | Selecione essa opção para permitir que o usuário edite a taxa de câmbio para despesas de cartão de crédito importadas.                                                                        |
|**Campos de hierarquia em vários níveis a serem exibidos**                  | Selecione os campos do aprovador que serão exibidos quando o tipo de atribuição de fluxo de trabalho de relatório de despesas for definido como a hierarquia e a seleção de hierarquia for definida para usar a hierarquia de aprovação de vários níveis Despesa. Quando a hierarquia de aprovação de vários níveis for usada para o fluxo de trabalho, os campos selecionados serão exibidos e editáveis no relatório Despesa. |
|**Inserir o número do cartão de crédito do funcionário (atualização de julho de 2017)**     | Selecione se um número com 15 ou 16 caracteres pode ser inserido e salvo no campo **ID do Cartão** na página **Cartões de crédito** de um funcionário.                                                                          |

### <a name="financial"></a>Financeiro

| **Campo**                                                            | **Descrição**     |
|----------------------------------------------------------------------|------------------------------------|
|**Nome de diário-razão**                                         | Selecione o nome do diário-razão onde serão lançados os relatórios de despesas aprovados.            |
|**Habilitar a restituição de imposto de despesas**                                  | Selecione essa opção para habilitar a restituição de imposto de despesas para as despesas qualificáveis. Essa opção não poderá ser habilitada se as regras de impostos e as regras de imposto sobre o uso dos EUA estiverem habilitadas.      |
|**Lançar adiantamentos em dinheiro imediatamente**                                     | Selecione essa opção para lançar um adiantamento em dinheiro aprovado quando o processo de Pagar e transferir estiver concluído. Se essa opção não for selecionada, o processo de Pagar e transferir gerará um diário geral não lançado. |
|**Data de contabilização correta durante lançamento**                             | Selecione essa opção para atualizar a data da contabilidade ao lançar despesas caso o período atual esteja em espera ou fechado. A data da contabilidade será definida como o próximo período em aberto.   |
|**Permitir o agrupamento de transações com base na contrapartida especificada no método de pagamento**      | Selecione essa opção para resumir as transações de despesas para um relatório de despesas, com base na contrapartida especificada no método de pagamento para as despesas.   
|**Imposto incluído**                                                   | Selecione essa opção para incluir por padrão o imposto no valor da despesa.             |
|**Liberar os ônus no fechamento das requisições de viagem**            | Selecione essa opção para liberar os fundos impedidos quando uma requisição de viagem aprovada for fechada.                                                                                   |
|**Permitir envio de requisição de viagem sobre orçamento excedido para registro de orçamento e orçamento de projeto** | Selecione essa opção para que os funcionários enviem requisições de viagem para aprovação que excedam o orçamento permitido definido no registro de orçamento ou o orçamento permitido para um projeto.            |
|**Permitir envio de relatório de despesas sobre orçamento excedido para registro de orçamento e orçamento de projeto**    | Selecione essa opção para permitir que os funcionários enviem para aprovação relatórios de viagem que excedam o orçamento permitido definido no registro de orçamento ou o orçamento permitido para um projeto.                |
|**Permitir aprovação de relatório de despesas sobre orçamento excedido somente para registro de orçamento**                | Selecione esta opção para permitir que os aprovadores aprovem os relatórios de despesa que excedam o orçamento permitido definido no registro de orçamento.                                                                       |

### <a name="per-diem"></a>Diária

| **Campo**                             | **Descrição**             |
|---------------------------------------|--------------------------------------------------------------------------------------|
|**Mínimo de horas para diária**           | Insira o número mínimo padrão de horas que um funcionário deve trabalhar em um dia para ser qualificado a receber uma diária para despesas relacionadas a viagens.  Esse valor é usado apenas como um valor padrão para o campo Mínimo de horas em camadas de taxas de diária.                                                                                      |
|**Porcentagem de refeição**                          | Insira a porcentagem padrão da diária para refeições usada no primeiro e no último dia da despesa relacionada à viagem quando o campo **Calcular a redução de refeição em** estiver definido como **Tipo de refeição por dia** ou **Número de refeições por dia**. O dia útil no primeiro e no último dia pode ser mais curto do que um dia útil. Portanto, o valor da diária nesses dias poderá ser diferente do valor padrão. Se a porcentagem for definida como 0, então as deduções do primeiro e do último dia serão 0,00. |
|**Porcentagem de hotel**                        | Insira a porcentagem padrão da diária para hotéis usada no primeiro e no último dia da despesa relacionada à viagem. O dia útil no primeiro e no último dia pode ser mais curto do que um dia útil. Portanto, o valor da diária nesses dias poderá ser diferente do valor padrão. Se a porcentagem for definida como 0, então as deduções do primeiro e do último dia serão 0,00.                                              |
|**Outra porcentagem**                        | Insira a porcentagem padrão da diária para despesas diversas usada no primeiro e no último dia da despesa relacionada à viagem. O dia útil no primeiro e no último dia pode ser mais curto do que um dia útil. Portanto, o valor da diária nesses dias poderá ser diferente do valor padrão. Se a porcentagem for definida como 0, então as deduções do primeiro e do último dia serão 0,00.                                                                                                     |
|**Redução da porcentagem para café da manhã** | Insira o valor da redução da diária para o café da manhã. Por exemplo, se um funcionário receber um café da manhã gratuito, talvez você queira reduzir o valor da diária em 10%.                               |
|**Redução da porcentagem para almoço**    | Insira o valor da redução da diária para o almoço. Por exemplo, se um funcionário receber um almoço gratuito, talvez você queira reduzir o valor da diária em 15%.                                       |
|**Redução da porcentagem para jantar**   | Insira o valor da redução da diária para o jantar. Por exemplo, se um funcionário receber um jantar gratuito, talvez você queira reduzir o valor da diária em 25%.                                     |
|**Calcular redução de refeições por**         | Escolha a forma como o sistema deve calcular a redução da diária de refeição ao selecionar se a redução se baseia no tipo de refeição por viagem ou por dia, ou se a redução se baseia no número de refeições permitidas por dia.|
|**Arredondamento da diária**                  | Selecione o tipo de arredondamento usado para despesas de diária. Se você selecionar o arredondamentos normal, todas as despesas de diária que tiverem um valor 0,50 serão arredondadas para 1,00, e todas as despesas de diária com um valor inferior a 0,50 serão arredondadas para 0,00.                                                                                              |
|**Basear o cálculo de diária em**         | Escolha se um valor de diária se baseará em um dia de calendário ou em um período de 24 horas.       |

### <a name="fax-cover-pages"></a>Folhas de rosto de fax

| **Campo**                      | **Descrição**            |
|--------------------------------|-----------------------------------------------------------------------------|
| **Instruções**                   | Insira as instruções que os funcionários devem seguir ao criar uma folha de rosto para um fax usado para enviar os recebimentos relacionados a um relatório de despesas. Clique no botão **Traduções** para inserir o texto do idioma específico que será exibido com base no idioma do usuário. |
|**ID do Usuário (Informações de código de barras)** | Selecione essa opção para armazenar o identificador exclusivo de um funcionário no código de barras usado na folha de rosto de fax.                 |
|**Código de barras**                      | Selecione o código de barras que será usado na folha de rosto de fax. Os códigos de barras 39 e 128 têm suporte do Gerenciamento de despesas.               |

### <a name="anti-corruption"></a>Anticorrupção

|                 <strong>Campo</strong>                 |                                                                                                                                                                                            <strong>Descrição</strong>                                                                                                                                                                                             |
|--------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <strong>Exibir atestado de anticorrupção</strong>  | Selecione essa opção para exibir o texto anticorrupção ao criar um novo relatório de despesas. As categorias de despesa específicas poderão então ser habilitadas e isso exigirá que o atestado de anticorrupção esteja selecionado no relatório de despesas. Por exemplo, uma categoria de presentes relacionada a uma despesa de autoridade do governo pode exigir que o funcionário confirme se a despesa atende à política da empresa relacionada a autoridades do governo. |
| <strong>Mensagem de anticorrupção para emissor</strong> |                                                                                             Insira texto que será exibido ao funcionário quando ele estiver criando um novo relatório de despesas. Clique no botão <strong>Traduções</strong> para inserir o texto do idioma específico que será exibido com base no idioma do usuário.                                                                                             |
| <strong>Mensagem de anticorrupção para aprovador</strong>  |                                                                                             Insira texto que será exibido ao aprovador quando ele estiver criando um novo relatório de despesas. Clique no botão <strong>Traduções</strong> para inserir o texto do idioma específico que será exibido com base no idioma do usuário.                                                                                             |


