---
title: Relatórios de arrendamento de ativos
description: Este tópico lista e descreve brevemente os relatórios disponíveis para arrendamento de ativos.
author: moaamer
manager: Ann Beebe
ms.date: 10/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-27
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4bc4bac1a422a7505ef4c66b9c3b79a3d754cc4d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971469"
---
# <a name="asset-leasing-reports"></a>Relatórios de arrendamento de ativos

[!include [banner](../includes/banner.md)]

Este tópico lista e descreve brevemente os relatórios disponíveis para arrendamento de ativos. A maioria dos relatórios é exibida ao concluir essas etapas ou etapas que são muito semelhantes, conforme observados. 

- Para exibir a maioria dos relatórios de arrendamento de ativos, vá para **Arrendamento de ativos > consultas e relatórios > relatórios de arrendamento** e selecione um relatório para exibir. Para os relatórios que exigem um caminho de seleção diferente, as etapas para abrir o relatório são incluídas na descrição desse relatório. 
- Quando você seleciona um relatório para imprimir, é aberta uma página de parâmetros que permite filtrar as informações incluídas no relatório. Insira os critérios de filtragem e selecione **OK** para gerar o relatório. O relatório gerado mostrará as informações que estão nos filtros especificados.

## <a name="asset-movement"></a>Movimento do ativo
O relatório de movimento de ativo serve como um relatório de roll forward para os saldos de ativo de direito de uso para cada arrendamento. Este relatório permite exibir as transações de ativos de um arrendamento durante um período específico. O relatório inclui os campos a seguir. 

|     Campos de relatório                  |     descrição                                                                |
|------------------------------------|--------------------------------------------------------------------------------|
|     Data de início              |     A data de início da versão mais antiga do arrendamento.                     |   
|     Prazo de arrendamento                     |     O prazo de arrendamento da versão mais antiga do arrendamento.                            |
|     Arrendamento de curto prazo               |     Se o arrendamento for classificado como um arrendamento de curto prazo, será exibido como **Sim**.         |
|     Arrendamento de baixo valor                |     Se o arrendamento for classificado como um arrendamento de baixo valor, será exibido como **Sim**.          |
|     Ativo de direito de uso     |     O valor original do ativo de direito de uso da entrada do diário de reconhecimento inicial.      |
|     Saldo inicial              |     O valor líquido contábil do ativo de direito de uso a partir da **Data inicial**.                         |
|     Despesa de depreciação de período    |     O valor da despesa de depreciação obtido no intervalo de datas definido para o relatório.        |
|     Depreciação Acumulada       |     O valor da depreciação acumulada a partir da **Data inicial**.                               |
|     Redução ao valor recuperável                     |     O valor do ativo foi recuperado no intervalo de datas definido para o relatório.               |
|     Modificações                  |     O valor dos ajustes do ativo de direito de uso entre os parâmetros de data.                            |
|     Valor líquido contábil                 |     O valor líquido contábil final do ativo de direito de uso, que é o líquido da depreciação acumulada a partir da **Data final**.    |

## <a name="differences-report"></a>Relatório de diferenças
O relatório de diferenças mostra as diferenças entre as informações carregadas na estrutura de importação de arrendamento e as informações que estão no sistema. Isso permite que você compare o que foi ajustado, atualizado ou adicionado por meio da estrutura de importação de arrendamento.  

Os valores no relatório irão variar com base no arrendamento selecionado. O relatório mostrará apenas os campos que diferem do que está atualmente no sistema e o que está nas tabelas de preparo. O valor antigo é o que está no sistema no momento ou o que estava anteriormente no sistema, dependendo da execução do processo de importação. O novo valor mostra o valor que está na tabela de preparo que substituirá o valor antigo.

## <a name="five-years-undiscounted-payment-forecast"></a>Previsão de pagamento não descontado de cinco anos
O relatório de previsão de pagamento descontado de cinco anos mostra os pagamentos de arrendamento descontados projetados a serem pagos durante os próximos cinco anos a partir da data especificada nos parâmetros do relatório. O relatório inclui os campos a seguir. 

|     Campos de relatório         |     descrição                                                                                       |
|-------------------------- |---------------------------------------------------------------------------------------------------    |
|     Descrição de arrendamento     |     A descrição do arrendamento do cabeçalho do arrendamento.                                                      |
|     ID do arrendamento              |     A ID exclusiva do arrendamento.                                                                              |
|     Reserva                  |     O registro de arrendamento associado à ID do registro.                                                         |
|     Classificação        |     A classificação do arrendamento.                                                                  |
|     Nível de Lançamento         |     A camada na qual esse arrendamento está sendo lançado.                                                         |
|     Moeda              |     A moeda do arrendamento.                                                                        |
|     Atual               |     A soma de todos os pagamentos de arrendamento a pagar nos próximos 12 meses a partir da data do relatório.          |
|     13-24 meses          |     A soma de todos os pagamentos de arrendamento entre 13 e 24 meses a partir da data do relatório.           |
|     25-36 meses          |     A soma de todos os pagamentos de arrendamento entre 25 e 36 meses a partir da data do relatório.           |
|     37-48 meses          |     A soma de todos os pagamentos de arrendamento entre 37 e 48 meses a partir da data do relatório.           |
|     49-60 meses          |     A soma de todos os pagamentos de arrendamento entre 49 e 60 meses a partir da data do relatório.           |
|     Depois disso            |     A soma de todos os pagamentos de arrendamento em ou após 61 meses a partir da data do relatório.              |

## <a name="gaap-cash-flows-report"></a>Relatório de fluxos de caixa GAAP
O relatório de divulgações do GAAP atende ao requisito de divulgação do GAAP dos EUA especificado em 842-20-50-4 (g) (1). Para exibir esse relatório, vá para **Arrendamento do Ativo > Consultas e relatórios > Divulgações > GAAP – fluxos de caixa**. 

|     Campos de relatório                                 |     descrição                                                                                                                                               |
|------------------------------------------------   |-----------------------------------------------------------------------------  |
|     Data Inicial <br> Data final                        |     Define um intervalo de datas usado para restringir as informações incluídas no relatório.      |
|     Entidade legal                                  |     A entidade legal ligada aos arrendamentos.                                      |
|     Tipo de arrendamento                                    |     A classificação do arrendamento como finanças ou operacional.           |
|     ID do arrendamento                                      |     A ID exclusiva do arrendamento.                                                      |
|     Descrição de arrendamento                             |     A descrição do arrendamento do cabeçalho do arrendamento.                              |
|     Registro de arrendamento                                    |     O registro de arrendamento para o qual a linha está se referindo.                        |
|     Nível de Lançamento                                 |     Cada registro anexado a um ativo fixo é configurado para um nível específico de lançamento que tem um objetivo de depreciação geral.                          |
|     Grupo de arrendamento                                   |     O grupo ao qual o arrendamento foi vinculado.                                     |
|     Moeda                                      |     A abreviação para a moeda da transação usada. Todos os relatórios converterão a moeda transacional na moeda do relatório.                      |
|     Arrendamento mercantil – fluxos de caixa operacionais         |     A soma do total de pagamentos variáveis lançados e os pagamentos de juros totais lançados a partir do plano de amortização entre os parâmetros de data.        |
|     Arrendamento mercantil – fluxos de caixa financeiros           |     A soma do total de pagamentos principais da agenda de amortização entre os parâmetros de data.       |
|     Arrendamento operacional – fluxos de caixa operacionais       |     A soma de todos os pagamentos de arrendamento lançados e pagamentos variáveis lançados entre os parâmetros de data.            |

## <a name="lease-balances-forecast"></a>Previsão de saldos de arrendamento
A previsão de saldos de arrendamento lista as informações diretamente da agenda de amortização de bens e da agenda de depreciação de ativos. O relatório mostra os valores previstos da responsabilidade de arrendamento projetado e os ativos de direito de uso durante um período de tempo, incluindo todas as despesas projetadas para esses arrendamentos. O relatório inclui os campos a seguir.

|     Campos de relatório                 |     descrição                                                                                                                                                                               |
|---------------------------------  |--------------------------------------------------------------------------------------------------------------------   |
|     Saldo inicial             |     O saldo inicial na agenda de amortização do arrendamento para o período que contém a data de início do relatório.            |
|     Reconhecimento inicial           |     Se a data de início do arrendamento cair no intervalo de datas definido para o relatório, esta coluna exibirá o valor da conta de passivo da entrada do diário de reconhecimento inicial.      |
|     Pagamentos                      |     A soma dos pagamentos da concessão que estão no intervalo de datas definido para o relatório.                               |
|     Interesse                      |     A soma das despesas de juros de arredamento que estão no intervalo de datas definido para o relatório.                    |
|     Saldo final                |     O saldo passivo do arrendamento a partir da **Data final**.                                                             |
|     Passivo de curto prazo          |     O valor de passivo de curto prazo no plano de amortização da concessão, a partir da **Data final**.                           |
|     Passivo de longo prazo           |     O valor de passivo de longo prazo na agenda de amortização da concessão, a partir da **Data final**.                            |
|     Valor contábil líquido inicial      |     O Valor Contábil Líquido Inicial na agenda de depreciação do ativo do arrendamento para o período que contém a data de início do relatório      |
|     Reconhecimento inicial           |     Se a data de início do arrendamento cair entre os parâmetros de data do relatório, esta coluna exibirá o valor da conta do ativo da entrada do diário de reconhecimento inicial.            |
|     Despesa de Depreciação          |     A soma das despesas de depreciação de arredamento que estão no intervalo de datas definido para o relatório.                  |
|     Saldo final                |     O saldo do ativo do arrendamento a partir da **Data final**.                                                              |
|     Ajuste de capital próprio             |     O saldo inicial menos o valor líquido contábil inicial.                                                             |

## <a name="lease-commencements-report"></a>Relatório de início do arrendamento
O relatório de inícios do arrendamento mostra todos os arrendamentos que foram iniciados em um intervalo de datas especificado, incluindo a responsabilidade inicial e os saldos de ativos de direito de uso. O relatório inclui os campos a seguir. 

|     Campos de relatório                 |     descrição                                                                                       |
|---------------------------------  |---------------------------------------------------------------------------------------------------    |
|     Data de início             |     A data da entrada do diário de reconhecimento inicial lançada para essa versão de arrendamento.         |
|     Valor do passivo inicial      |     O valor de passivo da entrada do diário de reconhecimento inicial.                                  |
|     Valor de ativo inicial          |     O valor do ativo de entrada do diário de reconhecimento inicial.                                      |

## <a name="lease-modification-report"></a>Relatório de modificação de arrendamento
O relatório de modificação de arrendamento mostra todos os arrendamentos que foram modificados em um intervalo de datas especificado. O relatório também mostra o usuário que ajustou o arrendamento e o valor total de responsabilidade ajustada. O relatório inclui os campos a seguir. 

|     Campos de relatório                 |     descrição           |
|---------------------------------  |-------------------------  |
|     Ajustado por                   |     O nome de usuário da pessoa que modificou o arrendamento.                                |
|     Ajuste               |     A data na qual a entrada de diário de ajuste foi lançada.                        |
|     Ajustes                   |     O valor de qualquer entrada de diário de ajuste lançado na conta de passivo do arrendamento entre os parâmetros de data. Os créditos aparecerão positivos, enquanto os débitos serão negativos.       |
|     Valor ganho (perda)            |     O valor de qualquer entrada de diário de ajuste lançado na conta de ganho/perda do arrendamento entre os parâmetros de data. Os créditos aparecerão positivos, enquanto os débitos serão negativos.       |
|     Lucros Retidos             |     O valor de qualquer entrada de diário de ajuste lançado na conta de ganhos retidos do arrendamento entre os parâmetros de data.      |
|     Saldo de responsabilidade final      |     O saldo de responsabilidade com arredondamento resultante a partir da data de ajuste do arrendamento.           |

## <a name="lease-movement-report"></a>Relatório de movimento do arrendamento
O relatório de movimento do arrendamento serve como um relatório de roll forward para os saldos com responsabilidade com arrendamento para cada arrendamento. Este relatório permite que o usuário exiba as transações de passivos de um arrendamento durante um período específico.

|     Campos de relatório             |     descrição                                               |
|----------------------------   |-------------------------------------------------------------- |
|     Data de início         |     A data de início da versão mais antiga do arrendamento.    |
|     Prazo de arrendamento                |     O prazo de arrendamento da versão mais antiga do arrendamento.           |
|     Pagamentos restantes        |     O número de pagamentos que ainda não foram lançados para o arrendamento.                       |
|     Saldo inicial         |     A soma de todas as transações que afetam a responsabilidade do arrendamento ocorrida antes da data de início do relatório.             |
|     Reconhecimento inicial       |     O valor de qualquer transação de reconhecimento inicial para o arrendamento lançado no intervalo de datas definido para o relatório.     |
|     Pagamentos                  |     A soma das transações de pagamento de arrendamento que foram lançados no intervalo de datas definido para o relatório. Os valores nesta coluna aparecerão como valores negativos, já que os pagamentos estão diminuindo o saldo de responsabilidade com arrendamento.  |
|     Interesse                  |     A soma das provisões de juros que foram lançadas no arrendamento dentro do intervalo de datas definido para o relatório.            |
|     Ajustes               |     A soma das transações de ajuste lançadas de arrendamento que estão no intervalo de datas definido para o relatório.                               |
|     Saldo final            |     O saldo de todas as transações de responsabilidade com arrendamento que foram lançadas a partir da **Data final** do relatório.                  |

## <a name="lease-transactions-report"></a>Relatório transações com arrendamento
A consulta de transações de arrendamento mostra todas as entradas de diário que foram geradas pelo arrendamento do ativo. Cada entrada de diário é vinculada à ID contábil da qual foi originada. Isso permite associar facilmente a entrada de diário com arrendamento correspondente. As funções de consulta de transações de arrendamento funciona de forma semelhante à página **Transações de comprovante** na contabilidade.

## <a name="weighted-average-discount-rate-report"></a>Relatório de taxa de desconto média ponderada
O relatório de taxa de desconto ponderada-médio atende ao requisito de divulgação de acordo com os EUA especificado em ASC 842-20-50-4 (g) (4) para uma taxa de desconto média ponderada. Para exibir esse relatório, vá para **Arrendamento do Ativo > Consultas e relatórios > Divulgações > Taxa de desconto da média ponderada**. O relatório inclui os campos a seguir. 

|     Campos de relatório                     |     descrição                                                           |
|------------------------------------   |------------------------------------------------------------------------   |
|     A partir da data                        |     Este relatório incluirá todos os arrendamentos que começaram em ou antes do parâmetro de data **A partir de**. Este relatório deve ser executado a partir do último dia do período a ser divulgado.      |
|     Pessoa jurídica em geral                      |     A entidade legal ligada ao arrendamento.                           |
|     ID do arrendamento                          |     A ID exclusiva do arrendamento.                                                  |
|     Descrição de arrendamento                 |     A descrição do arrendamento do cabeçalho do arrendamento.                          |
|     Reserva                              |     O tipo de livro específico do arrendamento exibido.                                                                                                                                            |
|     Nível de lançamento                     |     Cada registro anexado a um ativo fixo é configurado para um nível específico de lançamento que tem um objetivo de depreciação geral.      |
|     Grupo de arrendamento                       |     O grupo ao qual o arrendamento pertence.                                 |
|     Taxa de desconto                     |     A taxa usada para pagamentos de arrendamento de descontos.                             |
|     Moeda                          |     A abreviação para a moeda da transação usada. Todos os relatórios converterão a moeda transacional na moeda do relatório.  |
|     Pagamentos de arrendamento restantes          |     O valor total de pagamentos de arrendamento não pagos da agenda de pagamento restantes **A partir da** data.            |
|     Pagamentos ponderados restantes       |     Os pagamentos do arrendamento restantes multiplicados pela taxa de desconto usada.   |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]