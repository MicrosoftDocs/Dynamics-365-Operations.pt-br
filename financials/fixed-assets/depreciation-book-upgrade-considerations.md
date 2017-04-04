---
title: "Visão geral da atualização do registro de depreciações"
description: "Em versões anteriores, houve dois conceitos de ativos fixos - métodos e registros de depreciação. No Microsoft Dynamics 365 for Operations versão 1611, as funcionalidades de método de depreciação e de registro de depreciações foram mescladas em um único conceito que é conhecido como um registro. Este tópico fornece alguns aspectos a serem considerados durante a atualização."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer
ms.search.scope: Operations, Core
ms.custom: 221624
ms.assetid: cf434099-36f9-4b0f-a7c8-bed091e34f39
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: bec019d218d80ba059d5a1c232072f46b1ae3ee2
ms.openlocfilehash: d29cb7bc5acc29be93332b4211adebc4486a7a25
ms.lasthandoff: 03/31/2017


---

# <a name="depreciation-book-upgrade-overview"></a>Visão geral da atualização do registro de depreciações

Em versões anteriores, houve dois conceitos de ativos fixos - métodos e registros de depreciação. No Microsoft Dynamics 365 for Operations versão 1611, as funcionalidades de método de depreciação e de registro de depreciações foram mescladas em um único conceito que é conhecido como um registro. Este tópico fornece alguns aspectos a serem considerados durante a atualização. 

O processo de atualização moverá suas configurações existentes e todas as transações existentes para a nova estrutura de registro. Os métodos de depreciação são permanecerá como momento, como um registro que lançar na contabilidade. Os registros de depreciação serão movidos para um registro que tenha a opção **Lançar na contabilidade** definida como **Não**. Os nomes de diário de registro de depreciações serão movidos a um nome de diário de contabilidade com o nível de lançamento definido ** ** nenhum. Transações de registro de depreciação a serão movidas fixo transações de ativos. 

Antes de executar a atualização de dados, você deve entender as duas opções disponíveis para atualizar linhas do diário do registro de depreciação para comprovantes de transação, e a sequência numérica que será usada para a série de comprovante. 

Opção 1:  **Sequência numérica definida pelo sistema** – essa é a opção padrão para otimizar o desempenho da atualização. A atualização não usará a estrutura de sequência numérica, e em vez disso atribuirá comprovantes com uma abordagem baseada em conjuntos. Depois da atualização, a nova sequência numérica será criada com ** próximo número definido ** apropriadamente baseado em transações atualizadas. Por padrão, a sequência numérica será usada no formato de FADBUpgr\#\#\#\#\#\#\#\#\# . Há alguns parâmetros disponíveis a você ajustar o formato ao usar essa abordagem:

-   ** Numerar o código de sequência ** o código para identificar a sequência numérica. Esse código de sequência numérica não poderá existir desde que será criado pela atualização.
    -   Nome da constante: **NumberSequenceDefaultCode**
    -   Valor padrão: "FADBUpgr"
-   **Prefixo** – o valor da sequência de caracteres da constante que será usado como um prefixo para os números de comprovante.
    -   Nome da constante: **NumberSequenceDefaultParameterPrefix**
    -   Valor padrão: "FADBUpgr"
-   **Comprimento alfanumérico** – o comprimento do segmento alfanumérico da sequência numérica.
    -   Constante: nome ** NumberSequenceDefaultParameterAlpanumericLength **
    -   Valor padrão: 9
-   **Número inicial** – o primeiro número a ser usado na sequência numérica.
    -   Constante: nome ** NumberSequenceDefaultParameterStartNumber **
    -   Valor padrão: 1

Opção 2: ** A sequência definida por um usuário existente numérica ** - esta opção permitirá que você defina a seqüência numérica a ser usada para a atualização. Considere usar esta opção se precisar de configuração avançado de sequência numérica. Usar uma sequência numérica, modifique a classe ReleaseUpdateDB70\_FixedAssetJournalDepBookRemovalDepBookJournalTrans de atualização com as seguintes informações:

-   **Código da sequência numérica** – o código da sequência numérica.
    -   Constante: nome ** NumberSequenceExistingCode **
    -   Valor padrão: não há padrão, deve ser atualizado para o código da sequência numérica.
-   **Sequência numérica compartilhada** – um valor booliano para identificar o escopo da sequência numérica. Use "true" para sequências numéricas compartilhadas em todas as empresas e "false" para um escopo específico de uma empresa. Quando usar falsa “”, a sequência numérica com o nome especificado deve existir em cada empresa que contém transações de registro de depreciações. As sequências compartilhadas de existência em cada número partição que contém transações de registro de depreciações.
    -   Constante: nome ** NumberSequenceExistingIsShared **
    -   Valor padrão: true

Os parâmetros estão localizados no início de classe ReleaseUpdateDB70\_FixedAssetJournalDepBookRemovalDepBookJournalTrans. 

* Especifique uma abordagem de allocation* preferível 
* true de comprovantes, se desejar usar um code* 
existente de sequência numérica * falso, se pretender usar a seqüência numérica definida por padrão) * (const NumberSequenceUseExistingCode booleano falso; =  

* Se usando a abordagem definida pela sequência numérica, especifique os parâmetros para o número sequence.*
* uma nova sequência numérica será criada com esse parameters.* estreptococo NumberSequenceDefaultCode do const = “FADBUpgr;” estreptococo NumberSequenceDefaultParameterPrefix do const = “FADBUpgr;” const int NumberSequenceDefaultParameterAlpanumericLength; = 9 const int NumberSequenceDefaultParameterStartNumber; = 1   

* Se usando a abordagem existente de sequência numérica, especifique a sequência existente code.* 
* de número de comprovante a alocação irá rastreamento linha para o número sequences.* existente estreptococo NumberSequenceExistingCode do const ''; = * Especifique o escopo do 
existente code* de sequência numérica, * true se a sequência numérica especificada é shared* 
* falso, se a sequência numérica especificada é per-company* 
* a sequência definida por padrão de número será usada se um código de sequência numérica com o escopo especificado não for found.* const boolean NumberSequenceExistingIsShared = true; 

Recrie o projeto que contém a classe depois que as constantes forem modificadas. 

Durante a abordagem gerada pela sequência numérica padrão (1), a atualização do processamento definir- base para atribuir números de comprovante conforme especificado nos parâmetros de script de atualização. Também criará uma nova sequência numérica com parâmetros especificados após alocação. 

Ao usar a abordagem de sequência numérica existente definida pelo usuário (opção 2), a atualização de dados verifica se a sequência numérica com o escopo especificado existe no banco de dados para cada partição e empresa com transações do registro de depreciações. Caso exista, a atualização do processamento de rastreamento linha para atribuir números de comprovante conforme especificado pela sequência numérica com a estrutura da sequência numérica. Se a sequência numérica não existir com o escopo especificado, a atualização usará a abordagem definida por padrão de sequência numérica para atribuir números de comprovante, e cria uma nova sequência numérica com os parâmetros padrão especificado após alocação.

Em ambas abordagens, o script da atualização de dados também usará a sequência numérica para o campo **Série de comprovante** nos novos nomes de diário de contabilidade criados para os antigos nomes de diário de registro de depreciações.


