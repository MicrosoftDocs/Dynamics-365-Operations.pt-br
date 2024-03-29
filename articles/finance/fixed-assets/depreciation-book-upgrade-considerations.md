---
title: Visão geral do upgrade do registro de depreciações
description: Este artigo descreve o recurso do livro atual em Ativos fixos. Esse recurso baseia-se na funcionalidade anterior de modelo de valor que estava disponível em versões anteriores, mas também inclui todas as funcionalidade fornecidas anteriormente somente em registros de depreciação.
author: moaamer
ms.date: 06/20/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User, Developer
ms.reviewer: kfend
ms.custom:
- "221624"
- intro-internal
ms.assetid: cf434099-36f9-4b0f-a7c8-bed091e34f39
ms.search.region: global
ms.author: moaamer
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 784ec32ae886ef7ea9342b085f893eeeec761961
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8855481"
---
# <a name="depreciation-book-upgrade-overview"></a>Visão geral do upgrade do registro de depreciações

[!include [banner](../includes/banner.md)]

Este artigo descreve o recurso do livro atual em Ativos fixos. Esse recurso baseia-se na funcionalidade anterior de modelo de valor que estava disponível em versões anteriores, mas também inclui todas as funcionalidade fornecidas anteriormente somente em registros de depreciação. A funcionalidade de modelo de valor e registro de depreciação foram mescladas em um único conceito que é conhecido como registro. A funcionalidade do livro permite usar um único conjunto de páginas, consultas e relatórios para todos os processos de ativos fixos de sua organização. Este artigo fornece algumas informações a serem consideradas antes da atualização. 

O processo de atualização moverá suas configurações existentes e todas as transações existentes para a nova estrutura de registro. Os métodos de depreciação são permanecerá como momento, como um registro que lançar na contabilidade. Os registros de depreciação serão movidos para um registro que tenha a opção Lançar na contabilidade definida como Não. Os nomes de diário de registro de depreciações serão movidos a um nome de diário da contabilidade com o nível de lançamento definido como Nenhum. As transações do livro de depreciações serão movidas para as transações de ativo fixo.

Antes de executar a atualização de dados, você deve entender as duas opções disponíveis para atualizar linhas do diário do registro de depreciação para comprovantes de transação, e a sequência numérica que será usada para a série de comprovante.

Opção 1:  **Sequência numérica definida pelo sistema** – essa é a opção padrão para otimizar o desempenho da atualização. A atualização não usará a estrutura de sequência numérica, e em vez disso atribuirá comprovantes com uma abordagem baseada em conjuntos. Depois da atualização, a nova sequência numérica será criada com o **Conjunto do número seguinte** baseado apropriadamente nas transações de atualização. Por padrão, a sequência numérica será usada no formato de FADBUpgr\#\#\#\#\#\#\#\#\#. Há alguns parâmetros disponíveis para você ajustar o formato ao usar esta abordagem:

-   **Código da sequência numérica** – o código para identificar a sequência numérica. Esse código de sequência numérica não poderá existir, pois será criado pela atualização.
    -   Nome da constante: **NumberSequenceDefaultCode**
    -   Valor padrão: "FADBUpgr"
-   **Prefixo** – o valor da sequência de caracteres da constante que será usado como um prefixo para os números de comprovante.
    -   Nome da constante: **NumberSequenceDefaultParameterPrefix**
    -   Valor padrão: "FADBUpgr"
-   **Comprimento alfanumérico** – o comprimento do segmento alfanumérico da sequência numérica.
    -   Nome da constante: **NumberSequenceDefaultParameterAlpanumericLength**
    -   Valor padrão: 9
-   **Número inicial** – o primeiro número a ser usado na sequência numérica.
    -   Nome da constante: **NumberSequenceDefaultParameterStartNumber**
    -   Valor padrão: 1

Opção 2: **A sequência numérica definida por um usuário existente** - esta opção permitirá que você defina a sequência numérica a ser usada para a atualização. Use esta opção se precisar de configuração de sequência numérica avançada. Para usar uma sequência numérica, modifique a classe de atualização ReleaseUpdateDB70\_FixedAssetJournalDepBookRemovalDepBookJournalTrans com as seguintes informações:

-   **Código da sequência numérica** – o código da sequência numérica.
    -   Nome da constante: **NumberSequenceExistingCode**
    -   Valor padrão: não há padrão, deve ser atualizado para o código da sequência numérica.
-   **Sequência numérica compartilhada** – um valor Booliano para identificar o escopo da sequência numérica. Use "true" para sequências numéricas compartilhadas em todas as empresas e "false" para um escopo específico de uma empresa. Ao usar "falso", a sequência numérica com o nome especificado deverá existir em cada empresa que contenha as transações de registro de depreciações. Há sequências numéricas compartilhadas cada partição que contém transações de registro de depreciações.
    -   Nome da constante: **NumberSequenceExistingIsShared**
    -   Valor padrão: true

Os parâmetros estão localizados no início da classe ReleaseUpdateDB70\_FixedAssetJournalDepBookRemovalDepBookJournalTrans. 

*// Especifique uma abordagem de alocação de comprovantes* 
 *//true, se desejar usar um código de sequência numérica existente* 
 *// false, se quiser usar a sequência numérica definida pelo sistema (padrão)* const boolean NumberSequenceUseExistingCode = false;  

*// Se estiver usando a abordagem de sequência numérica definida pelo sistema, especifique os parâmetros para a sequência numérica.*
 *// Uma nova sequência numérica será criada com esses parâmetros.* const str NumberSequenceDefaultCode = 'FADBUpgr'; const str NumberSequenceDefaultParameterPrefix = 'FADBUpgr'; const int NumberSequenceDefaultParameterAlpanumericLength = 9; const int NumberSequenceDefaultParameterStartNumber = 1;   

*// Se estiver usando a abordagem de sequência numérica existente, especifique o código de sequência numérica existente.* 
 *// A alocação do comprovante irá linha por linha para as sequências numéricas existentes.* const str NumberSequenceExistingCode = ''; *// Especifica o escopo do código de sequência numérica existente* 
 *// true, se a sequência numérica especificada for compartilhada* 
 *// false, se a sequência numérica especificada for por empresa* 
 *// A sequência numérica definida pelo sistema padrão será usada se um código de sequência numérica com o escopo especificado não for encontrado.* const boolean NumberSequenceExistingIsShared = true; 

Recrie o projeto que contém a classe depois que as constantes forem modificadas. 

Ao usar a abordagem de sequência numérica gerada pelo sistema (opção 1), a atualização usará o processamento baseado no conjunto para alocar os números de comprovante, conforme especificado nos parâmetros de script de atualização. Também criará uma nova sequência numérica com parâmetros especificados após a alocação. 

Ao usar a abordagem de sequência numérica existente definida pelo usuário (opção 2), a atualização de dados verifica se a sequência numérica com o escopo especificado existe no banco de dados para cada partição e empresa com transações do registro de depreciações. Caso exista, a atualização usará o processamento linha por linha para alocar os números do comprovante, conforme especificado pela sequência numérica usando a estrutura da sequência numérica. Se a sequência numérica não existir com o escopo especificado, a atualização usará a abordagem de sequência numérica definida pelo sistema padrão para alocar os números de comprovante, e criará uma nova sequência numérica com os parâmetros padrão especificados após alocação.

Em ambas abordagens, o script da atualização de dados também usará a sequência numérica para o campo **Série de comprovante** nos novos nomes de diário de contabilidade criados para os antigos nomes de diário de registro de depreciações.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
