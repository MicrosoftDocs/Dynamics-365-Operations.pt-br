---
title: Configurar uma diretiva de localização para o registro da ordem de compra
description: Este tópico explica como configurar uma diretiva simples de local.
author: ShylaThompson
manager: tfehr
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSInventFixedLocation
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e9e7b8c1f5c5dfb29f1bdf28529ef76e31d8e83f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233622"
---
# <a name="set-up-a-location-directive-for-purchase-order-put-away"></a>Configurar uma diretiva de localização para o registro da ordem de compra

[!include [banner](../../includes/banner.md)]

Este tópico explica como configurar uma diretiva simples de local. O exemplo mostrado cria uma diretiva de localização a ser usada para determinar onde colocar os itens recebidos para uma ordem de compra. Você pode executar esse guia de tarefas com os dados mencionados utilizando a empresa de dados de demonstração USMF. Pré-condições: Você deve criar um código de disposição. Nesse procedimento usamos um código de disposição chamado Relabel. Se estiver criando uma diretiva de localização em seus próprios dados, você precisará configurar o gerenciamento de depósito avançado para seu depósito e seus itens. Esse procedimento é destinado ao gerente do depósito.

1. No painel de navegação, vá para **Módulos > Gerenciamento de depósito > Configuração > Diretivas de localização**.
2. No campo **Tipo de ordem de trabalho**, selecione **Ordens de compra**.

## <a name="create-a-location-directive-header"></a>Criar um cabeçalho da diretiva de localização
1. Selecione **Novo**.
2. No campo **Número de sequência**, insira um número. Essa é a sequência na qual a diretiva de localização é processada para o tipo de trabalho selecionado. Se necessário, você poderá também modificar a sequência.  
3. No campo **Nome**, digite um valor. Esse é o identificador exclusivo dessa diretiva.  
4. No campo **Tipo de trabalho**, selecione **Colocar**. Selecionar o tipo de trabalho a ser executado. Para diretiva com ordem de trabalho do tipo Ordem de compra, **Colocar** é o único valor aceito.  
5. No campo **Local**, digite um valor.
6. No campo **Depósito**, digite um valor. Deixe o Código diretivo vazio.  Códigos diretivos são usados para vincular uma linha da ordem de trabalho do tipo Colocado a uma diretiva específica. Para ordens de compra, a localização da última linha da ordem de trabalho do tipo Colocado é resolvida antes do modelo de trabalho ser determinado. Consequentemente não é possível conectar a última linha de um modelo de trabalho a uma diretiva específica.   
7. No campo **Código de descrição**, digite um valor. O Código de disposição limita o uso da diretiva de localização, de forma que a diretiva de localização seja usada somente se o funcionário do depósito inserir esse valor específico durante o registro do item usando um dispositivo móvel.  
8. Selecione **Salvar**.

## <a name="edit-the-query-for-directive"></a>Editar a consulta de diretiva
1. Selecione **Editar consulta**. O uso dessa diretiva já é limitado para ser usado pelos itens registrados no depósito especificado, e com o código de disposição especificado. Você pode adicionar outras restrições usando a consulta.  
2. Selecione **OK**.

## <a name="add-directive-lines"></a>Adicionar linhas diretivas
1. Selecione **Novo**. Essa é a sequência na qual as linhas diretivas da localização são processadas para o tipo de trabalho selecionado. Se necessário, você poderá também modificar a sequência.  
2. No campo **Da quantidade**, insira um número. Esta é a menor quantidade para a qual essa linha diretiva é válida.  
3. No campo **Até a quantidade**, insira um número.
4. No campo **Unidade**, digite um valor. A unidade em que as quantidades De e Até são expressadas. Se você deixar este campo em branco a unidade de estoque do item será usada.  
5. No campo **Localizar quantidade**, selecione uma opção.
    - Nenhum, ou quantidade da placa de licença: A quantidade registrada em cada placa de licença.  
    - Quantidade unitária: a quantidade inteira registrada.  
    - Quantidade restante: A quantidade que ainda precisa ser registrada da linha da ordem de compra.  
    - Quantidade esperada: A quantidade total que é especificada na linha da ordem de compra.  
6. Marque ou desmarque a caixa de seleção **Restringir por unidade**. Se você selecionar esta opção e especificar a unidade na página **Restringir por unidade**, somente os itens com essa unidade de medida poderão ser inseridos na localização. Por exemplo, se a unidade de medida for PL (paletes), somente os itens em paletes poderão ser inseridos na localização especificada.  
7. Marque ou desmarque a caixa de seleção **Permitir separação**. Isso permite que a diretiva separe a quantidade em várias localizações.  
8. Selecione **Salvar**.

## <a name="restrict-the-directive-line-to-a-specific-unit"></a>Restrinja a linha diretiva a uma unidade específica
1. Selecione **Restringir por unidade**. Este botão está disponível somente quando você pressiona **Salvar** após marcar a caixa de seleção **Restringir por unidade**.  
2. No campo **Unidade**, digite um valor.
3. Feche a página.

## <a name="add-a-location-directive-action-line"></a>Adicione uma linha de ação diretiva da localização
1. Selecione **Novo**. Essa é a sequência na qual as linhas de ação diretivas da localização são processadas para o tipo de trabalho selecionado. Se necessário, você poderá também modificar a sequência.  
2. No campo **Nome**, digite um valor. Esse é o identificador exclusivo dessa ação diretiva.  
3. No campo **Uso de localização fixa**, selecione uma opção.
    - Locais fixos e não fixos: todos os locais não fixos são válidos, bem como o local fixo do próprio produto, na faixa especificada na consulta.  
    - Somente localização fixa para o produto: As localizações fixas para o produto são válidas, e todas as variantes do produto compartilham o mesmo conjunto de localizações fixas.  
    - Somente localização fixa para as variantes do produto: Somente localizações fixas especificadas para cada variante do produto são válidas.  
4. No campo **Estratégia**, selecione uma opção. Ordens de serviço do tipo de ordem de compra oferecem suporte às estratégias a seguir: 
    - Nenhum: o item é colocado no primeiro local encontrado.  
    - Consolidar: O item é colocado em uma localização onde itens semelhantes já estão disponíveis.  
    - Local vazio sem trabalho de entrada: o item é colocado no primeiro local vazio encontrado. Uma localização será considerada vazia se não houver estoque físico e nenhum trabalho futuro esperado.  
5. Selecione **Salvar**.

## <a name="edit-the-query-for-directive-action-line"></a>Editar a consulta de linha de ação diretiva
1. Selecione **Editar consulta**.
2. Selecione **Adicionar**.
3. No campo **Campo**, digite `location profile ID`. Neste exemplo, os locais possíveis serão restritos por meio de uma ID de perfil de local.  
4. No campo **Critérios**, digite um valor.
5. Selecione **OK**. Você pode continuar adicionando linhas diretivas e ações diretivas até que você tenha considerado todos os possíveis cenários para o depósito.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]