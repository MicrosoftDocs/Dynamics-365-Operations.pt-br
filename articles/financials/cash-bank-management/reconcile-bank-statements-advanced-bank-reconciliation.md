---
title: "Reconciliar extratos bancários utilizando a reconciliação bancária avançada"
description: "O recurso Reconciliação bancária avançada permite que você importe extratos bancários eletrônicos e os reconcilie automaticamente com as transações bancárias do Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. Este tópico descreve o processo de reconciliação."
author: saraschi2
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 98243
ms.assetid: 9df13adf-aa9d-4f6b-bde6-25a214611692
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: b6c1b89256ab4b258f2901e47009a0eed573bd53
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="reconcile-bank-statements-by-using-advanced-bank-reconciliation"></a>Reconciliar extratos bancários usando reconciliação bancária avançada

[!include[banner](../includes/banner.md)]


O recurso Reconciliação bancária avançada permite que você importe extratos bancários eletrônicos e os reconcilie automaticamente com as transações bancárias do Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. Este tópico descreve o processo de reconciliação.  

<a name="import-an-electronic-bank-statement"></a>Importar um extrato bancário eletrônico
-----------------------------------

Você importa seu extrato bancário utilizando a ação **Importar extrato** na página **Extratos bancários**. A conta bancária é identificada no extrato bancário por meio de uma combinação de valores que estão definidos nos detalhes da conta bancária. Esses valores incluem o nome do banco, o número da conta bancária, número de roteamento, código da Sociedade de Telecomunicações Financeiras Interbancárias Mundiais (SWIFT), e o Número Internacional de Conta Bancária (IBAN). 

Você pode carregar um extrato bancário que contém informações sobre uma única conta ou várias contas. Se houver mais contas, as contas podem estar em entidades legais diferentes.

-   Para importar um arquivo de extrato bancário único sobre uma única conta, defina a opção **Importar extrato para múltiplas contas bancárias em todas entidades legais** para **Não**, e selecione a conta bancária associada ao extrato. Clique em **Procurar** para selecionar o arquivo de extrato bancário associado e, em seguida, clique em **Carregar**.
-   Para importar um arquivo de extrato bancário único sobre várias contas, defina a opção **Importar extrato para múltiplas contas bancárias em todas entidades legais** para **Sim**. Clique em **Procurar** para selecionar o arquivo de extrato bancário associado e, em seguida, clique em **Carregar**.

Se nenhuma instruções no arquivo eletrônico não podem ser associadas com uma conta bancária usando os campos de identificação, não serão importados. No entanto, outras instruções em arquivo ainda podem ser importados. O usuário receberá uma mensagem para os que a importação de extrato bancário foi malsucedida para contas bancárias específicas. Observe que o usuário que está importando o arquivo de extrato bancário deve ter acesso a uma entidade legal às instruções de importação para contas bancárias da entidade legal. 

Você também pode zipar um arquivo para carregar vários arquivos de extrato para o Finanças e Operações em um único processo usando um arquivo zip. Para importar vários arquivos de extrato bancário sobre várias contas, combine todos os arquivos de extrato bancário em um arquivo zip. Na caixa de diálogo **Importar extratos bancários**, defina a opção **Importar extrato para múltiplas contas bancárias em todas entidades legais** para **Sim**. Clique em **Procurar** para selecionar o arquivo zip que contém os arquivos de extratos bancários e, em seguida, clique em **Carregar**. O processo de importação reconhecerá o arquivo relevante e cobrar cada demonstrativo que estão incluídas nele, independentemente de entidade legal da conta bancária. 

A opção **Reconciliar após a importação** está disponível. Quando essa opção está definida como **Sim**, o sistema automaticamente valida o extrato bancário, cria uma nova reconciliação bancária e planilha, e executa o conjunto de regras de correspondência padrão assim que o extrato bancário é carregado. Essa funcionalidade automatiza o processo até o ponto em que as transações devem ser correspondidas manualmente.

## <a name="validate-the-bank-statement"></a>Validar o extrato bancário
Para validar um extrato, clique em **Validar** na página **Extratos bancários**. Extratos bancários devem ser validados antes que possam ser reconciliados. Esta etapa será concluída automaticamente se a opção **Reconciliar após a importação** estava definida como **Sim** no momento da importação. 

A validação de extrato bancário verifica os seguintes detalhes:

-   O extrato bancário corresponde à conta bancária selecionada.
-   A moeda do extrato bancário corresponde à moeda da conta bancária.
-   O saldo inicial do extrato é igual ao saldo final do extrato anterior para essa conta bancária.
-   A data não se sobrepõe à data de um extrato bancário diferente para a mesma conta bancária.
-   Não existem intervalos entre as datas dos extratos para a conta bancária.
-   As datas nas linhas do extrato estão entre as datas de início e fim do extrato bancário.
-   O saldo inicial e os valores das linhas resumidas se igualam ao saldo final.

Quando a validação estiver concluída, o status do extrato bancário é atualizado para **Validado**. Um extrato bancário deve ser validado antes que possa ser reconciliado.

## <a name="reconcile-the-bank-statement"></a>Reconciliar o extrato bancário
Depois de importar um extrato bancário eletrônico e validá-lo na página **Extratos bancários**, você pode reconciliar o extrato bancário utilizando as páginas **Reconciliação bancária** e **Planilha de reconciliação bancária**. 

Na página **Reconciliação bancária**, clique em **Novo** para criar uma nova reconciliação e, em seguida, selecione a conta bancária do extrato que foi importado. Uma conta bancária pode ter apenas uma reconciliação bancária aberta. A data de fechamento determina as transações do extrato bancário e transações bancárias do Operations que estão inclusas na planilha de reconciliação. Por padrão, a data atual do sistema é usada como data de fechamento, mas é possível alterar a data para a reconciliação. As informações restantes do cabeçalho são automaticamente retiradas do extrato. Esta etapa será concluída automaticamente se a opção **Reconciliar após a importação** estava definida como **Sim** no momento da importação. 

Na página **Reconciliação bancária**, clique em **Planilha** para abrir a página **Planilha de reconciliação bancária**. Se a opção **Reconciliar após a importação** estava definida como **Sim**, o conjunto de regras de correspondência padrão é executado automaticamente para a reconciliação. Para executar manualmente as regras de correspondência, clique em **Executar regras de correspondência** para selecionar os conjuntos de regras de correspondência para executar sobre as transações bancárias. Caso tenho muitas transações para processar, é possível concluir essa etapa como um processo em lote. 

A página **Planilha de reconciliação bancária** possui quatro grades que contém transações. As duas grades superiores mostram transações do extrato bancário e do Operations que ainda não foram correspondidas. As duas grades inferiores mostram transações correspondidas. A guia **Detalhes de transação do extrato bancário** mostra detalhes sobre a transação do extrato bancário não correspondida selecionada na grade superior. 

Existem três maneiras de corresponder ou reconciliar transações do extrato bancário:

-   Corresponder as transações com transações bancárias do Operations.
-   Corresponder as transações com uma transação de extrato bancário de estorno.
-   Marcar as transações como **Novo**, de modo que possam ser lançadas posteriormente como uma transação bancária no Finanças e Operações.

Para combinar as transações manualmente, selecione as transações na grade **Transações do extrato bancário**, selecione as transações correspondentes na grade **Transações bancárias do Operations** e clique em **Corresponder**. As transações selecionadas são movidas das grades superiores, para transações não correspondidas, para as grades inferiores, que representam as transações correspondidas. Além disso, os valores totais correspondidos e não correspondidos são atualizados. É possível obter combinações de transações um para um, várias para um e várias para várias. As correspondências devem seguir as regras para as diferenças de data permitidas e mapeamento do tipo de transação. Essas regras são definidas na página **Parâmetros de gerenciamento de banco e caixa**.

Poderão ocorrer diferenças mínimas na sua reconciliação. É possível combinar uma única transação do extrato bancário e uma única transação bancária do Operations que possuem diferenças mínimas, caso essas diferenças estejam dentro do valor tolerado definido no campo **Diferença mínima permitida** na conta bancária. O valor é mostrado no campo **Valor da correção** na transação bancária do Operations correspondente. Quando a reconciliação bancária é marcada como reconciliado, correções são lançadas automaticamente usando a conta principal definido no tipo de transação associado bancárias. Correções não são suportadas para **Cheque** e **Depósito** tipos de documento. 

As transações de estorno do extrato bancário são correspondidas utilizando a planilha de reconciliação. Duas linhas do extrato podem podem ser combinadas se os valores forem opostos e se uma das transações está marcada como um estorno. Também é possível definir uma regra de correspondência para a ação **Limpar linhas de estorno do extrato**.

Transações bancárias estornadas do Operations devem ser reconciliadas utilizando a página **Transações bancárias do Operations**. É possível reconciliar duas transações bancárias do Operations juntas se os documentos tiverem a mesma conta bancária, o mesmo tipo de documento, a mesma referência de pagamento, e se tiverem valores opostos. Também é possível reconciliar um cheque único cancelado para prevenir que essas transações apareçam na planilha de reconciliação. 

Se existem novas transações iniciadas pelo banco, como juros, taxas e tarifas, que ainda não estão no Finanças e Operações, você pode adicioná-las à um diário que está associado à reconciliação do extrato bancário selecionado. Selecione uma transação do extrato bancário na grade **Transações do extrato bancário** de transações não combinadas e, em seguida, clique em **Marcar como nova**. O status da transação é definido como **Nova**, e a transação será movida para a grade **Transações do extrato bancário** que representa as transações combinadas. Você irá lançar as transações marcadas como **Nova** posteriormente, pela página **Extrato bancário**. 

É possível desfazer a combinação de transações que foram combinadas incorretamente. Selecione a transação do extrato bancário combinada e, em seguida, clique em **Desfazer combinação**. Todas as transações associadas são movidas de volta às grades superiores para transações não combinadas, e os valores totais combinados e não combinados são atualizados. 

Depois de concluir seu processo de reconciliação, você deve marcar a Planilha de reconciliação bancária como reconciliada.  Este processo lança automaticamente os valores de correção usando as contas definidas na página **Tipo de transação bancária** .  A reconciliação bancária para um demonstrativo pode ser marcada como reconciliada a qualquer momento, mesmo se houver linhas de extrato bancário que ainda não foram correspondidas.  As transações não correspondidas serão movidas automaticamente para a próxima planilha de reconciliação, conforme s transações de extrato bancário são reconciliadas.  Observe que depois que uma reconciliação de extrato bancário foi marcada como reconciliada, ela não poderá ser desfeita.  A reconciliação não será editável e não terá a capacidade de fazer atualizações à reconciliação.

## <a name="post-new-transactions-that-are-associated-with-the-reconciliation"></a>Lançar novas transações associadas à reconciliação
As transações do extrato bancário que foram marcados como **Nova** na planilha de reconciliação são lançadas na página **Extrato bancário**. Na página **Extrato bancário**, selecione a ID do extrato para exibir os detalhes do extrato. No menu **Contabilidade**, é possível usar as opções **Exibir distribuições** e **Exibir contabilidade** para exibir os detalhes por trás das novas transações e as entradas contábeis associadas. Selecione a opção **Lançar** para lançar as linhas do extrato bancário marcadas como **Nova** à contabilidade. É importante observar que o lançamento só pode ser concluído uma única vez por extrato bancário.




