---
title: Introdução ao arrendamento de ativos
description: Este tópico descreve o recurso Arrendamento de ativos e percorre as etapas para criar um arrendamento de ativos e exibir informações para esses arrendamentos.
author: moaamer
manager: Ann Beebe
ms.date: 09/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-09-24
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 5f8f86861f65f3da71843f6fd4a64e4199e86627
ms.sourcegitcommit: 9668af8d918faec37abe1881e550872cd6b73259
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/08/2020
ms.locfileid: "3969999"
---
# <a name="asset-leasing-get-started"></a>Introdução ao arrendamento de ativos

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tópico descreve o recurso Arrendamento de ativos e percorre as etapas para criar um arrendamento de ativos e exibir informações para esses arrendamentos. O tópico também define a terminologia usada na interface do usuário e na documentação. O arrendamento de ativos é um recurso avançado para gerenciar, rastrear e automatizar transações financeiras do locatário para ativos arrendados no Microsoft Dynamics 365 Finance. O arrendamento de ativos está em conformidade com padrões internacionais de contabilidade (IFRS 16) e padrões de GAAP dos EUA (ASC 842). O arrendamento de ativos captura e processa informações sobre os arrendamentos e ajuda a gerar entradas de diário durante o ciclo de vida da concessão das entradas de reconhecimento inicial, de diário mensal, para deficiências e encerramento da concessão. O arrendamento de ativos se integra perfeitamente a outros componentes do Dynamics 365 Finance, incluindo Ativos fixos, Contas a pagar e Contabilidade.

Para obter mais informações sobre padrões contábeis, consulte a documentação padrão para IFRS 16 e GAAP dos EUA (ASC 842).

## <a name="asset-leasing-elements"></a>Elementos de locação de ativo
O diagrama a seguir mostra os principais elementos do processo comercial para arrendamentos.

[![Elementos de locação de ativo](./media/overview-01.png)](./media/overview-01.png)

Um ativo arrendado contém os seguintes componentes principais:

- **Contrato de arrendamento** - o arrendador é proprietário do ativo e concorda com o menos para conceder um ativo ao período específico em troca de pagamentos de arrendamento periódico. Além do contrato legal entre o locador e menos, o contrato de arrendamento captura decisões de gerenciamento, como a probabilidade de exercer uma opção de renovação e transferência de propriedade.

- **Cálculo de arrendamento e classificação por padrão contábil** - o cálculo e a classificação do arrendamento identificam o padrão contábil que será aplicado na medição inicial e posterior, bem como o teste de classificação que determina qual será o tipo de arrendamento. Um arrendamento pode ser um arrendamento financeiro, um arrendamento operacional, um arrendamento de curto prazo ou um arrendamento de valor baixo. O sistema também calcula o valor presente de pagamentos de arrendamento mínimos futuros com a finalidade de avaliação e classificação.

- **Transações de arrendamento** - o arrendamento de ativos oferece suporte ao reconhecimento inicial do ativo de direito de uso para arrendamentos no balanço, bem como uma medida subsequente para arrendamentos no balanço ou de arrendamentos fora do balanço. A transação de reconhecimento inicial mede o valor presente de pagamentos de arrendamento mínimos futuros. Esses dados são usados para determinar o valor do ativo e a responsabilidade de arrendamento iniciais, que afetam o balanço da organização. A medição subsequente das transações de arrendamento mensal envolve o acúmulo de interesse na responsabilidade com arrendamento, o que aumenta a responsabilidade com arrendamento. Ele também mede a provisão de pagamentos do arrendamento que diminuem a responsabilidade com arrendamento e que, posteriormente, será pago ao locador. A medida também inclui a amortização do ativo de direito de uso.

  Para arrendamentos fora do balanço, o sistema calcula a despesa de arrendamento linear de acordo com o que for menor: a vida útil econômica do ativo ou o prazo de arrendamento. Os ajustes de arrendamento medem modificações de contrato como uma extensão ou expansão de arrendamento e a transação de redução ao valor recuperável que usa o ativo de direito de uso para custos não recuperáveis.

  O arrendamento de ativos integra-se com a Contabilidade para garantir que todas as transações de arrendamento lançadas atualizem seu plano de contas. O arrendamento de ativos se integra a Contas a pagar para rastrear faturas do arrendador em Contas a pagar e fazer pagamentos futuros a partir daí. A integração com Ativos fixos permite rastrear arrendamento no registro de ativos fixos e lançar transações de ativos de direito de uso, incluindo o reconhecimento inicial, a depreciação e a redução ao valor recuperável do ativo, de dentro de Ativos fixos.   

## <a name="asset-leasing-components"></a>Componentes de arrendamento de ativos 
A concessão de ativos mapeia informações de arrendamento, planos de pagamento, datas inicial e final e a frequência de pagamento. Ele também automatiza cálculos para valor presente, pagamentos mensais do arrendamento, juros e amortização de arrendamento. O sistema executa os testes de classificação de arrendamento, dependendo da configuração. O sistema também cria e lança as transações de arrendamento correspondentes, que se baseiam na estrutura definida pelo padrão contábil que você está seguindo.

O diagrama a seguir mostra o registro de arrendamento, a concessão, o plano de pagamento calculado, os testes de classificação para arrendamentos e os registros de arrendamento e as transações contábeis correspondentes.

[![Arrendamento, registro de arrendamento e plano de pagamento](./media/overview-02.png)](./media/overview-02.png)

- **Registro de arrendamento** - o registro de arrendamento inclui todas as informações sobre o contrato de arrendamento, como prazos de arrendamento, valor justo e pagamentos do arrendamento. Ele também inclui o padrão contábil que você está seguindo, o tipo de arrendamento e os limites que são considerados no teste de classificação do arrendamento. O registro de arrendamento também contém as transações de arrendamento lançadas na contabilidade. 
  
- **Arrendamento** - o arrendamento transporta as informações de concessão de ativo que representam a base do arrendamento de ativo, a fonte de informações de arrendamento é composta pelo contrato de arrendamento e pela decisão da gerência, ambos feitos fora do Dynamics 365 Finance. O valor justo do ativo é o preço que seria pago por um ativo em uma transação na data de medida. Esse valor pode depender do tipo de ativo, das condições de mercado e de outros critérios que possam ser considerados na avaliação. O valor justo do ativo será considerado na equação do teste de classificação.

- **Vida útil do ativo** - representa os períodos restantes da vida útil de um ativo, a partir da data de início do arrendamento. A vida útil de um ativo será considerada na equação do teste de classificação. Ela difere da vida útil definida em Ativos fixos.

- **Taxa incremental de empréstimo** - é a taxa de juros que será usada para calcular o valor presente. O sistema usará a taxa implícita, se estiver definido nos dados do arrendamento, para calcular o valor presente dos pagamentos do arrendamento. Se a taxa implícita não for definida, o sistema usará a taxa incremental de empréstimo.

- **Tipo de anuidade** - é o pagamento de arrendamento devido no início do período de pagamento ou no final do período. Isso pode ser pagamento em adiantamento ou anuidade devido (no início do período de pagamento do arrendamento) ou anuidade comum (ao final do período de pagamento do arrendamento).

  O primeiro mês será considerado número de período zero para pagamento antecipado; o primeiro mês será considerado o período um para o atraso de pagamento.

- **Intervalo de composição** - representa os períodos numéricos em que os juros são compostos por ano. Isso pode ser mensal (12 períodos por ano), trimestral (4 períodos por ano), semestral (2 períodos por ano) ou anual (1 período por ano). O número de períodos será considerado no cálculo do valor presente.

- **Data de início** - é a data que o arrendador disponibiliza o ativo para uso pelo arrendatário. Todos os cálculos e transações de arrendamento serão baseados na data de início. A data de início deve ficar no começo de um período (primeiro dia do mês) para garantir a precisão dos cálculos subsequentes. Você pode usar o campo **Data de assinatura do contrato** para inserir a data real em que o contrato foi assinado.

- **Prazo de arrendamento** - é a extensão do período de arrendamento, em meses.

> [!NOTE] 
> A definição do prazo de arrendamento é baseada no número de períodos, ou intervalos, nas linhas do plano de pagamento. O número definido de intervalos será convertido em meses.

- **Linha do plano de pagamento** - captura os pagamentos do arrendamento por período. Também especifica se um período de renovação será exercido e incluído na medida inicial do ativo de direito de uso e responsabilidade com arrendamento. Você pode definir a data de início dos pagamentos de arrendamento vencidos e os intervalos de período que representam a extensão do arrendamento, que pode ser dias, meses ou anos.

- **Frequência de pagamento** - indica se o pagamento é mensal, trimestral, semestral ou anual. A data de término é calculada automaticamente com base na data de início e no número de períodos inseridos.

- **Plano de pagamento** - é o valor presente calculado, com base no período de tempo coberto pelos pagamentos do arrendamento, pelo valor dos pagamentos, pelos períodos compostos e pelo tipo de anuidade.

- **Períodos** - são os períodos de arrendamento que refletem o tipo de composição interna e de anuidade. O intervalo de composição determina como os períodos serão divididos. Você pode definir os seguintes intervalos de composição:

  - Mensal, 12 períodos por ano
  - Trimestral, 4 períodos por ano
  - Semestral, 2 períodos por ano
  - Anual, 1 período por ano

O primeiro período será iniciado com o período zero, se o tipo de anuidade for devido. Caso contrário, o primeiro período será iniciado com um, se o tipo de anuidade for atraso de pagamento.

- **Meses** - indica o número de meses do calendário durante o período de arrendamento. O valor do pagamento é o valor devido definido na frequência de pagamento. O valor presente calculado é o pagamento do arrendamento baseado em valor presente por período, os intervalos de composição e a taxa de empréstimo incremental.

> [!NOTE] 
> O valor presente é calculado com base na equação de fluxo de caixa descontada.

- **Registros** - é a configuração predefinida que será associada a cada arrendamento. O registro define o padrão contábil aplicado, os tipos de arrendamento e o limite que é usado como base para os testes de classificação. Os testes de classificação são usados para especificar o tipo de arrendamento automaticamente.

- **Estrutura contábil** - mostra o padrão contábil selecionado, IFRS 16 ou ASC 842, aos quais você está oferecendo suporte. O padrão contábil é designado no registro associado ao arrendamento. O padrão de contabilidade determinará as contas contábeis especificadas no perfil de lançamento.

- **Tipos de arrendamento** indica qual dos dois tipos de arrendamento será usado, seja um arrendamento mercantil ou um arrendamento operacional. Sob um arrendamento mercantil, os riscos e recompensas relacionados ao ativo arrendado são transferidos para o arrendatário. Sob um arrendamento operacional, os riscos e recompensas relacionados ao ativo arrendado permanecem com o arrendador. Uma terceira opção é uma identificação automatizada do tipo de , seja mercantil ou operacional, com base nos limites definidos no registro. Essa identificação automática é realizada durante o teste de reclassificação do arrendamento.

- **Limites** - usado nos testes de classificação de arrendamento para determinar se o ativo é classificado como uma das seguintes opções:

  - **Prazo de arrendamento** - é a porcentagem da vida útil a ser usada no teste de classificação. O sistema classificará o arrendamento como mercantil se o tipo de arrendamento for definido como automático e se o prazo de arrendamento sobre a vida útil do ativo for maior ou igual ao percentual definido aqui.

  - **Valor presente** - é a porcentagem do valor justo do ativo a ser usada no teste de classificação. O sistema classificará o arrendamento como mercantil se o tipo de arrendamento for definido como automático e se o valor presente de pagamentos do arrendamento futuros sobre o valor justo do ativo for maior ou igual ao percentual definido aqui.

  - **Arrendamento de curto prazo** - se o prazo de arrendamento for menor ou igual ao valor definido, o arrendamento será classificado como um arrendamento de curto prazo.

  - **Baixo valor** - se o valor justo do ativo for menor ou igual ao valor definido, o arrendamento será classificado como um arrendamento de baixo valor.

  - **Classificação e transações de arrendamento** - a classificação de arrendamento é um processo automatizado para classificar os arrendamento com base nos limites definidos nos registros, além de outros critérios de teste de classificação para identificar se o arrendamento é um arrendamento mercantil, um arrendamento operacional, um arrendamento de curto prazo ou arrendamento de baixo valor. Isso também é usado para identificar se o processo de arrendamento diferido é seguido.

Os testes de classificação incluem a Transferência de propriedade, a Opção de compra, o Prazo de arrendamento, o Valor presente e o Ativo exclusivo. O diagrama a seguir ilustra os testes de classificação de arrendamento.

[![Testes de classificação de arrendamento](./media/overview-03.png)](./media/overview-03.png)

Cada tipo de arrendamento controla a contabilidade de modo diferente para transações de arrendamento diferentes. As transações incluem o reconhecimento inicial, despesas de juros, pagamento de vencimento de arrendamento e depreciação de arrendamento, e são baseadas nos padrões contábeis que você está seguindo (IFRS 16 ou ASC 842). As contas contábeis são definidas no perfil de lançamentos de arrendamento para cada tipo de transação e estrutura contábil.

## <a name="asset-leasing-transactions"></a>Transações de arrendamento de ativos

#### <a name="initial-recognition"></a>Reconhecimento inicial 
O reconhecimento inicial de um ativo arrendado usa o valor presente calculado para que possa ser relatado no balanço. A entrada contábil para isso é gerada automaticamente. Essa transação debita da conta de ativo de direito de uso e credita na conta de responsabilidade do arrendamento operacional da seguinte maneira. Se um ativo fixo for associado ao arrendamento, a entrada de reconhecimento inicial será refletida como uma aquisição de ativo fixo. Neste cenário, você deve definir um perfil de lançamentos de ativos fixos para lançar na conta de ativo de direito de uso. 

> [!NOTE]
> Os arrendamentos operacionais são aceitos apenas pelo US GAAP ASC 842.

|     Tipo                                          |     Débito                     |     Crédito                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Arrendamento operacional sob US GAAP              |     Ativo de direito de uso      |     Responsabilidade com arrendamento operacional       |
|     Arrendamento mercantil sob IFRS e US GAAP        |     Ativo de direito de uso      |     Responsabilidade com arrendamento operacional       |

#### <a name="lease-liability-amortization-interest-expense"></a>Amortização de responsabilidade com arrendamento (despesa de juros) 
Os juros de um arrendamento são reconhecidos pelo cálculo de juros para o saldo inicial do arrendamento, pagamento de arrendamento do período, taxa de empréstimo de juros e períodos de intervalo composto por ano. O valor dos juros aumenta a conta de responsabilidade arrendada operacional ao creditar nela, o que será refletido no balanço da organização. A transação também inclui uma entrada de débito na conta de despesas de juros, que é refletida no demonstrativo de lucros e perdas para arrendamento mercantis e para a conta de despesas de arrendamento para arrendamentos operacionais.

|     Tipo                                          |     Débito                     |     Crédito                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Entrada de responsabilidade de arrendamento operacional em US GAAP ASC 842    |     Despesa de Juros          |     Responsabilidade com arrendamento operacional         |
|     Entrada de responsabilidade com arrendamento mercantil sob IFRS e US GAAP      |     Despesa de Juros          |     Responsabilidade com arrendamento mercantil           |

#### <a name="accrued-lease-payment"></a>Pagamento de arrendamento acumulado
Um pagamento de arrendamento acumulado é reconhecido como um pagamento futuro de arrendamento que deve ser processado como uma transação de pagamento das contas bancárias ou de caixa. A conclusão do pagamento do arrendamento diminui a responsabilidade com arrendamento ao debitar da conta de responsabilidade de arrendamento de um razão auxiliar de fornecedor no caso de o arrendador ser definido como fornecedor, ou ao lançar o lado de crédito em uma conta contábil de notas a pagar, então o pagamento será executado em relação ao fornecedor ou às notas a pagar.

|     Tipo                                          |     Débito                     |     Crédito                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Arrendamento operacional sob US GAAP              |  Responsabilidade com arrendamento operacional    |   Responsabilidade do fornecedor (razão auxiliar)/Notas a pagar  |
|     Arrendamento mercantil sob IFRS e US GAAP        |  Responsabilidade com arrendamento mercantil      |   Responsabilidade do fornecedor (razão auxiliar)/Notas a pagar  |

#### <a name="asset-depreciation"></a>Depreciação de ativo
O ativo de uso de direito é depreciado sobre o que for menor - a vida útil do ativo ou o prazo de arrendamento. O método para calcular a depreciação para US GAAP (ASC 842) se baseia na diferença entre a despesa de arrendamento linear e o valor dos juros. Os juros sobre arrendamentos mercantis são calculados usando um método linear padrão. A depreciação de arrendamento afeta o demonstrativo de lucros e perdas, debitando da despesa de juros. O balanço é afetado pelo crédito da conta de ativo de direito de uso acumulada para arrendamentos mercantis. Para arrendamentos operacionais, a depreciação é creditada na conta de despesas de arrendamento. Se o arrendamento estiver vinculado a um ativo fixo, as transações de depreciação serão executadas somente do módulo de ativos fixos. 

|     Tipo                                          |     Débito                     |     Crédito                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Arrendamento operacional sob US GAAP              |  Despesa de arrendamento                |   Depreciação acumulada de ativo de direito de uso     |
|     Arrendamento mercantil sob IFRS e US GAAP        |   Depreciação de despesa de ativo de direito de uso   |   Depreciação acumulada de ativo de direito de uso    |

#### <a name="short-term-lease"></a>Arrendamento de curto prazo
Um arrendamento de curto prazo é reconhecido como uma despesa, o que afetará o demonstrativo de lucros de uma organização. O pagamento do arrendamento gerado por vencimento irá debitar da conta de despesas de arrendamento e creditar na conta de notas a pagar ou de razão auxiliar do fornecedor.

|     Tipo                                          |     Débito                     |     Crédito                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Entrada de arrendamento de curto prazo sob IFRS e US GAAP     |  Despesa de arrendamento                |   Responsabilidade do fornecedor (razão auxiliar)/Notas a pagar  |

#### <a name="low-value-lease"></a>Arrendamento de baixo valor
Um arrendamento de baixo valor é reconhecido como uma despesa que afetará o demonstrativo de lucros da sua organização. O pagamento do arrendamento gerado por vencimento irá debitar da despesa de arrendamento e creditar nas notas a pagar ou na razão auxiliar do fornecedor.

|     Tipo                                          |     Débito                     |     Crédito                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Entrada de arrendamento de baixo valor sob IFRS e US GAAP      |  Despesa de arrendamento                |   Responsabilidade do fornecedor (razão auxiliar)/Notas a pagar  |


#### <a name="index-revaluation"></a>Reavaliação de índice
Esta é a conta de arrendamento de ativos para pagamentos do arrendamento variável medidos por uma taxa indexada. As alterações em pagamentos do arrendamento causadas por flutuações de taxa indexada constituem um ajuste de arrendamento sob o IFRS 16. A responsabilidade com arrendamento e os ativos de direito de uso serão ajustados para a conta dos novos pagamentos. 

|     Tipo                                          |     Débito                             |     Crédito                    |
|-----------------------------------------------    |-------------------------------------  |----------------------------   |
|   Entrada de reavaliação do índice no IFRS em caso de aumento  |  Ativo de direito de uso       |   Responsabilidade com arrendamento operacional |
|   Entrada de reavaliação do índice no IFRS em caso de redução  |  Responsabilidade com arrendamento operacional  |   Ativo de direito de uso      |

Quando os pagamentos são alterados por causa de uma alteração na taxa indexada, somente os pagamentos variáveis serão alterados, a menos que haja alterações adicionais nos fluxos de caixa, como uma alteração nas condições de arrendamento relacionadas às taxas de juros sob US GAAP 842 ASC.

#### <a name="lease-adjustment"></a>Ajuste de arrendamento
O arrendamento de ativos permite que as concessões sejam ajustadas se os termos de arrendamento forem modificados, o arrendamento for estendido ou se houver circunstâncias adicionais sob as quais um arrendamento exija um ajuste. Os ajustes de arrendamento são lançados para aumentar ou diminuir o ativo de direito de uso e a responsabilidade com arrendamento. O processo de ajuste utiliza saldos finais acumulados de amortização de passivos e saldo de ativos na data de ajuste. Quando um arrendamento estiver vinculada ao ativo fixo, o ajuste de direito de uso será lançado usando a ID atribuída em Ativos fixos. 

|     Tipo                                          |     Débito                             |     Crédito                    |
|-----------------------------------------------    |-------------------------------------  |----------------------------   |
|   Entrada de ajuste de arrendamento para IFRS e GAAP no caso de aumento     |  Ativo de direito de uso       |   Responsabilidade com arrendamento operacional |
|   Entrada de ajuste de arrendamento para IFRS e GAAP no caso de redução     |  Responsabilidade com arrendamento operacional  |   Ativo de direito de uso      |


#### <a name="lease-impairment"></a>Redução ao valor recuperável de arrendamento
Isso representa a redução de saldo acumulado do ativo de direito de uso. Identifique o valor da redução ao valor recuperável, a data da transação e os períodos restantes. O ativo de direito de uso restante será amortizado de forma linear. A lógica de redução ao valor recuperável de arrendamento considera o valor acumulado do ativo que existe no plano de depreciação de ativos.  

|     Tipo                                          |     Débito                             |     Crédito                    |
|-----------------------------------------------    |-------------------------------------  |----------------------------   |
|   Entrada de redução ao valor recuperável para IFRS e US GAAP           |  Despesa de redução ao valor recuperável                   |    Ativo de direito de uso     |

>[!NOTE]
> Se o arrendamento estiver vinculado a um ativo fixo, o redução ao valor recuperável de arrendamento deverá ser lançado de Ativos fixos porque a depreciação de ativo é executada no módulo Ativos fixos.

**Moeda dupla** As transações de arrendamento podem ser lançadas em uma moeda diferente da moeda contábil e do relatório. A taxa de câmbio da moeda é definida na Contabilidade na data de início. Você pode alterar as taxas de câmbio definindo o campo **Taxa fixa** como **Sim** ao criar o arrendamento. Quando você insere transações de arrendamento, as transações de depreciação iniciais e de reclassificação subsequentes usarão a taxa de câmbio da data de início. As transações de pagamento e de juros subsequentes usarão a taxa de câmbio ativa atual. 

## <a name="create-an-asset-lease"></a>Criar um arrendamento de ativo
Conclua as etapas a seguir para criar um novo arrendamento. 

1. Para usar o **Arrendamento de ativo**, você deverá habilitá-lo no espaço de trabalho **Gerenciamento de recursos**. No espaço de trabalho **Gerenciamento de recursos**, selecione **Tudo** para que todos os recursos estejam listados na página. Selecione **Arrendamento de ativo** e selecione **Habilitar agora**.
2. Vá para **Arrendamento de ativo > Comum > Resumo do arrendamento**. Insira nos campos necessários na Guia Rápida **Geral**. 
   - **Detalhes do arrendamento**
   - **Vida útil do ativo (meses)**
   - **Grupo de arrendamento**
   - **Taxa incremental de empréstimo (%)**
   - **Intervalo de composição**
   - **Tipo de anuidade**
   - **Moeda**
   - **Data de início**

3. Mude para a Guia Rápida **Linhas do plano de pagamento** e insira uma linha de pagamento e, em seguida, selecione **Criar agendas**.

4. Selecione **Registros**. 

5. Alterne para a Guia Rápida **Geral**. O **Ativo de direito de uso inicial** e a **responsabilidade com arrendamento** são calculados. 

6. Vá para a Guia Rápida **Teste de classificação de arrendamento** para verificar o valor no campo **Tipo de arrendamento**. 

   O **Tipo de arrendamento** é classificado com base nos critérios definidos na página **Registros**.

7.  Vá para **Plano de pagamento** na seção **Função**.  

   A página **Plano de pagamento** lista futuros planos de pagamento para uma ID de arrendamento. Selecione **Confirmar plano** para poder lançar as transações de **Reconhecimento inicial**. 

[![Função de reconhecimento inicial](./media/overview-13.png)](./media/overview-13.png)

8. Selecione **Reconhecimento inicial** para criar o diário de reconhecimento inicial. 

9. Selecione **Diários de arrendamento de ativo** para lançar a transação de reconhecimento inicial. 

   Do plano de pagamento, você poderá abrir uma página detalhada que lista as transações de ativos de direito de uso. 
 
   O **Plano de amortização da responsabilidade com arrendamento** mostra o valor dos juros calculado para cada período.
   
10. Crie o diário e vá para **Diários de arrendamento de ativo**. O **Plano de amortização de responsabilidade com arrendamento** também é exibido nas transações de juros.

   A página **Plano de depreciação de ativos** mostra as transações de depreciação para a ID do arrendamento selecionada. 

   [![Página Transações de ativo DDU](./media/overview-20.png)](./media/overview-20.png)

   A página **Transações de ativo DDU** lista o reconhecimento inicial, a depreciação acumulada e o saldo do ativo. 

   A página **Transações de responsabilidade com arrendamento** mostra o reconhecimento inicial, o pagamento de juros de arrendamento, o pagamento do arrendamento e o saldo da responsabilidade com arrendamento. 

