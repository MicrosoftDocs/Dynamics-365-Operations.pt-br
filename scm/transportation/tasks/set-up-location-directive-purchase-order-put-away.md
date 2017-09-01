--- 
title: "Configurar uma diretiva de localização para o armazenamento da ordem de compra"
description: "Este procedimento mostra como configurar uma diretiva de localização simples."
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 4c2456fffd9a010728154749b35c58db13f142bb
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-a-location-directive-for-purchase-order-put-away"></a>Configurar uma diretiva de localização para o armazenamento da ordem de compra

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como configurar uma diretiva de localização simples. O exemplo mostrado cria uma diretiva de localização a ser usada para determinar onde colocar os itens recebidos referentes a uma ordem de compra. Você pode executar esse guia de tarefas com os dados mencionados utilizando a empresa de dados de demonstração USMF. Pré-condições: Você deve criar um código de disposição. Nesse procedimento usamos um código de disposição chamado Relabel. Se você estiver criando uma diretiva de localização em seus próprios dados, você precisa configurar o gerenciamento de depósito avançado para o depósito e seus itens.  Esse procedimento é destinado ao gerente do depósito.

1. Vá para Gerenciamento de depósito > Configuração > Diretivas de local.
2. No campo Tipo de ordem de trabalho, selecione 'Ordens de compra'.

## <a name="create-a-location-directive-header"></a>Criar um cabeçalho da diretiva de localização
1. Clique em Novo.
2. No campo de número de sequência, insira um número.
    * Essa é a sequência na qual a diretiva de localização é processada para o tipo de trabalho selecionado. Se necessário, você poderá também modificar a sequência.  
3. No campo Nome, digite um valor.
    * Esse é o identificador exclusivo dessa diretiva.  
4. No campo Tipo de trabalho, selecione 'Colocar'.
    * Selecionar o tipo de trabalho a ser executado. Para diretiva com ordem de trabalho do tipo Ordem de compra, Colocar é o único valor aceito.  
5. No campo Local, digite um valor.
6. No campo Depósito, digite um valor.
    * Deixe o Código diretivo vazio.  Códigos diretivos são usados para vincular uma linha da ordem de trabalho do tipo Colocado a uma diretiva específica. Para ordens de compra, a localização da última linha da ordem de trabalho do tipo Colocado é resolvida antes do modelo de trabalho ser determinado. Consequentemente não é possível conectar a última linha de um modelo de trabalho a uma diretiva específica.   
7. No campo Código de descrição, digite um valor.
    * O Código de disposição limita o uso da diretiva de localização, de forma que a diretiva de localização seja usada somente se o funcionário do depósito inserir esse valor específico durante o registro do item usando um dispositivo móvel.  
8. Clique em Salvar.

## <a name="edit-the-query-for-directive"></a>Editar a consulta de diretiva
1. Clique em Editar consulta.
    * O uso dessa diretiva já é limitado para ser usado pelos itens registrados no depósito especificado, e com o código de disposição especificado. Você pode adicionar outras restrições usando a consulta.  
2. Clique em OK.

## <a name="add-directive-lines"></a>Adicionar linhas diretivas
1. Clique em Novo.
    * Essa é a sequência na qual as linhas diretivas da localização são processadas para o tipo de trabalho selecionado. Se necessário, você poderá também modificar a sequência.  
2. No campo Da quantidade, insira um número.
    * Esta é a menor quantidade para a qual essa linha diretiva é válida.  
3. No campo Até a quantidade, insira um número.
4. No campo Unidade, digite um valor.
    * A unidade em que as quantidades De e Até são expressadas. Se você deixar este campo em branco a unidade de estoque do item será usada.  
5. No campo Localizar quantidade, selecione uma opção.
    * Nenhum, ou quantidade da placa de licença: a quantidade registrada em cada placa de licença. Quantidade inutilizada: Toda a quantidade registrada. Quantidade restante: A quantidade que ainda precisa ser registrada da linha da ordem de compra. Quantidade esperada: A quantidade total que é especificada na linha da ordem de compra.  
6. Marque ou desmarque a caixa de seleção Restringir por unidade.
    * Se você selecionar esta opção e especificar a unidade na página Restringir por unidade, somente os itens com essa unidade de medida poderão ser inseridos na localização. Por exemplo, se a unidade de medida for PL (paletes), somente os itens em paletes poderão ser inseridos na localização especificada.  
7. Marque ou desmarque a caixa de seleção Permitir separação.
    * Isso permite que a diretiva separe a quantidade em várias localizações.  
8. Clique em Salvar.

## <a name="restrict-the-directive-line-to-a-specific-unit"></a>Restrinja a linha diretiva a uma unidade específica
1. Clique em Restringir por unidade.
    * Este botão está disponível somente quando você pressiona Salvar após marcar a caixa de seleção Restringir por unidade.  
2. No campo Unidade, digite um valor.
3. Feche a página.

## <a name="add-a-location-directive-action-line"></a>Adicione uma linha de ação diretiva da localização
1. Clique em Novo.
    * Essa é a sequência na qual as linhas de ação diretivas da localização são processadas para o tipo de trabalho selecionado. Se necessário, você poderá também modificar a sequência.  
2. No campo Nome, digite um valor.
    * Esse é o identificador exclusivo dessa ação diretiva.  
3. No campo Uso de localização fixa, selecione uma opção.
    * Localizações fixas e não fixas: Todas as localizações não fixas são válidas, bem como a localização fixa do produto, dentro do intervalo especificado na consulta.  Somente localização fixa para o produto: As localizações fixas para o produto são válidas, e todas as variantes do produto compartilham o mesmo conjunto de localizações fixas. Somente localização fixa para as variantes do produto: Somente localizações fixas especificadas para cada variante do produto são válidas.  
4. No campo Estratégia, selecione uma opção.
    * Ordens de trabalho do tipo Ordem de compra suportam as seguintes estratégias: Nenhum: o item é colocado na primeira localização encontrada. Consolidar: O item é colocado em uma localização onde itens semelhantes já estão disponíveis. Localização vazia sem trabalho futuro: o item é colocado na primeira localização vazia encontrada. Uma localização será considerada vazia se não houver estoque físico e nenhum trabalho futuro esperado.  
5. Clique em Salvar.

## <a name="edit-the-query-for-directive-action-line"></a>Editar a consulta de linha de ação diretiva
1. Clique em Editar consulta.
2. Clique em Adicionar.
3. No campo Campo, digite 'ID do perfil de localização'.
    * Neste exemplo, iremos restringir as localizações possíveis utilizando um ID do perfil de localização.  
4. No campo Critérios, digite um valor.
5. Clique em OK.
    * Você pode continuar adicionando linhas diretivas e ações diretivas até que você tenha considerado todos os possíveis cenários para o depósito.  


