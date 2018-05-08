--- 
title: Configurar um modelo de trabalho para ordens de compra
description: "Este procedimento tem como foco a configuração de um modelo de trabalho simples que será usado no armazenamento dos itens recebidos."
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: fbbe019bdca2d5182466a20370418a14032fe63d
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-a-work-template-for-purchase-orders"></a>Configurar um modelo de trabalho para ordens de compra

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento tem como foco a configuração de um modelo de trabalho simples que será usado no armazenamento dos itens recebidos. Modelos de trabalho determinam o conjunto de instruções apresentadas ao trabalhador do depósito em um dispositivo móvel ao mover itens da área de recebimento. Você pode usar esse procedimento com os dados mencionados na empresa de dados de demonstração USMF. Antes de iniciar este guia, crie uma ID de grupo de trabalho. Neste exemplo, uma ID de grupo de trabalho chamada na Entrada é usada. Esse procedimento é destinado ao gerente do depósito.

1. Vá para Gerenciamento de depósito > Configuração > Trabalho > Modelos de trabalho.
2. No campo Tipo de ordem de trabalho, selecione 'Ordens de compra'.

## <a name="create-a-work-template-header"></a>Criar um cabeçalho do modelo de trabalho
1. Clique em Novo.
2. No campo de número de sequência, insira um número.
    * Esta é a sequência em que os modelos de trabalho são avaliados. Você pode modificar a sequência, se necessário.  
3. No campo Modelo de trabalho, digite um valor.
    * Este é o identificador exclusivo desse modelo.  
4. No campo Descrição do modelo do trabalho, digite um valor.
    * A opção Válido não será marcada até que você tenha concluído todas as informações exigidas pelo modelo e, depois, tenha clicado em Salvar.  
    * Uma ordem de trabalho do tipo Ordem de compra não pode ser processada automaticamente. Por isso, deixa a opção Processar automaticamente definida como Não.  
5. No campo ID de grupo de trabalho, digite um valor.
    * As IDs de grupo de trabalho permitem organizar o trabalho em grupos. O valor definido aqui será o valor padrão de qualquer trabalho criado usando esse modelo.  
6. No campo Prioridade de trabalho, insira '1'.
    * Isso indica a importância do trabalho, e o valor que você definiu aqui será o padrão de qualquer trabalho criado com esse modelo.  
7. Clique em Salvar.
    * Você deve salvar o cabeçalho do modelo de trabalho antes que o botão Editar consulta fique disponível.  

## <a name="set-up-the-query-for-the-work-template"></a>Configurar a consulta do modelo de trabalho
1. Clique em Editar consulta.
    * Definiremos uma limitação segundo a qual o modelo só pode ser usado em um depósito específico.  
2. Clique em Adicionar.
3. Na lista, marque a linha selecionada.
4. No campo Campo, digite 'depósito'.
5. No campo Critérios, digite um valor.
6. Clique em OK.
7. Clique em Sim.

## <a name="set-work-template-details"></a>Definir detalhes do modelo de trabalho
1. Clique em Novo.
2. No campo Tipo de trabalho, selecione 'Separar'.
3. No campo ID de classe de trabalho, digite 'compra'.
    * A classe de trabalho definida aqui será a padrão em todas as linhas de trabalho de tipo Separar criadas com esse modelo. A classe de trabalho não pode ser substituída nas linhas da ordem de trabalho. Classes de trabalho são usadas para direcionar e/ou limitar os tipos de linhas da ordem de trabalho que um funcionário do depósito pode processar em um dispositivo móvel.  
4. Clique em Novo.
5. No campo Tipo de trabalho, selecione 'Colocar'.
6. No campo ID de classe de trabalho, digite um valor.
    * As instruções de separação e armazenamento formam um conjunto. Cada conjunto separar/armazenar deve ter a mesma classe de trabalho. Use a mesma classe de trabalho que você forneceu para a instrução de separação.  
7. Clique em Salvar.
    * Note que agora a caixa de seleção Válido está marcada.  


