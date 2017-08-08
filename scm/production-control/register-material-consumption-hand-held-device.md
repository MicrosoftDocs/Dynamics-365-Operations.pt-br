---
title: "Registrar o consumo de materiais usando um dispositivo móvel"
description: "Este tópico descreve um fluxo de trabalho que permite o registro do consumo de matéria-prima na produção usando um dispositivo portátil."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: AX 7.0.0, Operations, UnifiedOperations
ms.custom: 1706093
ms.assetid: 75ee68e0-4b9f-4f4d-b286-f498e0eb73fa
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: b4c0d14340e96b2e7916ea73e25e62ae5c33ce49
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---

# <a name="register-material-consumption-using-a-mobile-device"></a>Registrar o consumo de materiais usando um dispositivo móvel
Este tópico descreve um fluxo de trabalho que permite o registro do consumo de matéria-prima na produção usando um dispositivo portátil.

<a name="introduction"></a>Introdução
------------

Este fluxo de trabalho é relevante se houver um requisito rigoroso para a rastreabilidade do material. Nesses casos, para manter a rastreabilidade dos materiais, o tempo e a quantidade exatos devem ser relatados para o consumo. Este processo pode ser visto em oposição às operações de pré-lavagem ou retrocesso, onde há um deslocamento entre o momento do registro e o tempo em que o consumo real ocorre. Isso explica por que uma estratégia de consumo automático não pode ser usada para alguns materiais com requisitos de rastreabilidade. Vejamos um cenário simples que explica como configurar um fluxo de trabalho para permitir o registro do consumo de matéria-prima na produção, usando um dispositivo portátil. [![](./media/scenario3.png)](./media/scenario3.png)

### <a name="scenario-details"></a>Detalhes do cenário

Um processo contínuo de produção (5) consome a matéria-prima controlada por lote RM-100. O material está disponível no local Bulk-001 (1) na placa PL-1 com dois lotes, B1 e B2, ambos com uma quantidade de 100 lbs. O trabalho de depósito (2) é liberado e processado para RM-100 e o material é colhido de Bulk-001 para o local de entrada de produção PIL-01 (3), que é definido como não-placa de matrícula controlada. O operador da máquina pesa o material do local de entrada de produção (3) e registra o peso e o número do lote como consumido (4). Do local de entrada de produção, uma parte do material é adicionada manualmente ao processo de produção em intervalos de tempo definidos. Quando o operador da máquina adiciona material, é pesado em uma escala e o número do lote é registrado.

## <a name="set-up-the-workflow-to-register-consumption-using-a-handheld-device"></a>Configure o fluxo de trabalho para registrar o consumo usando um dispositivo de mão
Crie um produto acabado-bom, FG-100, com uma lista de materiais que possui a matéria-prima MR-100 controlada por lote. Adicione dois lotes, B1 e B2, de RM-100 em uma quantidade de 100 para o local: Bulk-001 na placa: PL-1. O princípio de liberação na linha da lista de materiais para RM-100 é **Manual**. Defina a localização da entrada de produção para PIL-01. Você pode fazer isso selecionando esta localização como a localização de entrada de produção padrão no depósito 51.

1.  Crie um novo item de menu de dispositivo móvel: 

-    **Nome do item de menu** - Registrar consumo de material. 
-    **Título** - Registrar consumo de material. 
-    **Modo** - Indireto. 
-    **Código de atividade** - Registrar consumo de material.

2.  Adicione o item de menu ao menu de dispositivo **Produção móvel**.
3.  Crie uma ordem de produção para o produto concluído: 

-    **Número do item** - FG-100 
-    **Local** - 5 
-    **Depósito** - 51 
-    **Quantidade** - 150

A ordem de produção é **Estimada** e **Liberada** e o trabalho de depósito é criado.

4.  Complete o trabalho usando o fluxo de trabalho para a escolha da matéria-prima para o dispositivo portátil.

Isso trará o material da localização em massa para o local de entrada de produção PIL-01. Depois que o trabalho for concluído, o material terá o status **Escolhido no local de entrada de produção**. O status depois que os trabalhos foram processados pode ser **Separado** ou **Reservado**. Isso é configurado com o parâmetro **Status da emissão depois de colocar no formulário do depósito**.

5.  Inicie a ordem de produção a partir do cliente ou do dispositivo portátil usando o item de menu **Início da produção**.

Depois que a ordem de produção for iniciada, você pode registrar o consumo de material com o fluxo de trabalho do dispositivo portátil. Vamos começar registrando o consumo de 25 lbs do lote B1.

6.  Selecione o item de menu **Registrar consumo de** **material** no menu para o dispositivo portátil, e insira os seguintes detalhes: 

-    O número da ordem de produção. 
-    A localização em que o material será consumido, neste caso PIL-01. 
-    Número do item RM-100. 
-    Nº do lote B1. 
-    Uma quantidade de 25.

7.  Selecione **OK**.

Observe que a mensagem "Linha do diário criada" aparece no visor. Na ordem de produção há um diário aberto do tipo **Lista de separação da produção** para o número de item RM-100 e o número de lote B1. 

Agora você pode escolher continuar o registro, por exemplo, o número de lote B2, e toda vez que você selecionar **OK,** uma nova linha de diário será adicionada ao diário aberto. 

Após concluir o registro, selecione **Feito** para lançar o diário e termine o fluxo de trabalho.

### <a name="additional-comments"></a>Comentários adicionais 

-   Se um usuário cancelar o fluxo de trabalho após a criação de uma linha de diário, o diário fica em um estado não posicionado, mas se o usuário em um ponto posterior usar o fluxo de trabalho para a mesma ordem de produção, as linhas serão adicionadas ao diário aberto, em vez de um novo diário.
-   O novo fluxo de trabalho também suporta o registro de números de série.
-   Só é possível registrar um número de item definido na lista de materiais ou na fórmula para a ordem de produção selecionada ou a ordem do lote.
-   O material pode ser consumido em excesso. Por exemplo, se for estimado que o material será consumido com a quantidade de 100 libras, então pode ser consumido em excesso com uma quantidade de, por exemplo, 105 libras.



