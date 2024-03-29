---
title: Registrar o consumo de materiais usando um dispositivo móvel
description: Este artigo descreve um fluxo de trabalho que permite o registro do consumo de matéria-prima na produção usando um dispositivo portátil.
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1706093
ms.assetid: 75ee68e0-4b9f-4f4d-b286-f498e0eb73fa
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1e1dbc399eb06d1049950bbdd755b479ef275563
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849232"
---
# <a name="register-material-consumption-using-a-mobile-device"></a>Registrar o consumo de materiais usando um dispositivo móvel

[!include [banner](../includes/banner.md)]

Este artigo descreve um fluxo de trabalho que permite o registro do consumo de matéria-prima na produção usando um dispositivo portátil.

## <a name="introduction"></a>Introdução

Este fluxo de trabalho é relevante se houver um requisito rigoroso para a rastreabilidade de materiais. Nesses casos, para manter a rastreabilidade dos materiais, o tempo e a quantidade exatos devem ser relatados para o consumo. Este processo pode ser visto em oposição às operações de pré-lavagem ou retrocesso, onde há um deslocamento entre o momento do registro e o tempo em que o consumo real ocorre. Isso explica por que uma estratégia de consumo automático não pode ser usada para alguns materiais com requisitos de rastreabilidade. Vejamos um cenário simples que explica como configurar um fluxo de trabalho para permitir o registro do consumo de matéria-prima na produção, usando um dispositivo portátil. [![configurar um fluxo de trabalho para habilitar o registro de consumo de matéria-prima usando um dispositivo portátil.](./media/scenario3.png)](./media/scenario3.png)

### <a name="scenario-details"></a>Detalhes do cenário

Um processo contínuo de produção (5) consome a matéria-prima controlada por lote RM-100. O material está disponível no local Bulk-001 (1) na placa PL-1 com dois lotes, B1 e B2, ambos com uma quantidade de 100 lbs. O trabalho de depósito (2) é liberado e processado para RM-100 e o material é colhido de Bulk-001 para o local de entrada de produção PIL-01 (3), que é definido como não-placa de matrícula controlada. O operador da máquina pesa o material do local de entrada de produção (3) e registra o peso e o número do lote como consumido (4). Do local de entrada de produção, uma parte do material é adicionada manualmente ao processo de produção em intervalos de tempo definidos. Quando o operador da máquina adiciona material, é pesado em uma escala e o número do lote é registrado.

## <a name="set-up-the-workflow-to-register-consumption-using-a-handheld-device"></a>Configurar o fluxo de trabalho para registrar o consumo usando um dispositivo portátil
Crie um produto de mercadoria concluída, FG-100, com uma lista de materiais que tenha a matéria-prima controlada por lote RM-100. Adicione dois lotes, B1 e B2, de RM-100 em uma quantidade de 100 ao local: Bulk-001 na placa de licença: PL-1. O princípio de liberação na linha da lista de materiais para RM-100 é **Manual**. Defina o local de entrada de produção como PIL-01. Você pode fazer isso selecionando esta localização como a localização de entrada de produção padrão no depósito 51.

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

Isso trará o material da localização em massa para o local de entrada de produção PIL-01. Depois que o trabalho for concluído, o material terá o status **Separado no local de entrada de produção**. O status depois que os trabalhos foram processados pode ser **Separado** ou **Reservado**. Isso é configurado com o parâmetro **Status da emissão depois de colocar no formulário do depósito**.

5.  Inicie a ordem de produção a partir do cliente ou do dispositivo portátil usando o item de menu **Início da produção**.

Depois que a ordem de produção for iniciada, você pode registrar o consumo de material com o fluxo de trabalho do dispositivo portátil. Vamos começar registrando o consumo de 25 lbs do lote B1.

6.  Selecione o item de menu **Registrar consumo de** **material** no menu para o dispositivo portátil e insira os seguintes detalhes: 

-    O número da ordem de produção. 
-    A localização em que o material será consumido, neste caso PIL-01. 
-    Número do item RM-100. 
-    Nº do lote B1. 
-    Uma quantidade de 25.

7.  Selecione **OK**.

Observe que a mensagem "Linha do diário criada" aparece na tela. Na ordem de produção há um diário aberto do tipo **Lista de separação da produção** para o número de item RM-100 e o número de lote B1. 

Agora você pode escolher continuar o registro, por exemplo, o número de lote B2, e toda vez que você selecionar **OK,** uma nova linha de diário será adicionada ao diário aberto. 

Após concluir o registro, selecione **Concluído** para lançar o diário e encerrar o fluxo de trabalho.

### <a name="additional-comments"></a>Comentários adicionais 

-   Se um usuário cancelar o fluxo de trabalho após a criação de uma linha de diário, o diário ficará em um estado não lançado, mas, se o usuário posteriormente usar o fluxo de trabalho para a mesma ordem de produção, as linhas serão adicionadas ao diário aberto, em vez de um novo diário.
-   O novo fluxo de trabalho também oferece suporte ao registro de números de série.
-   Só é possível registrar um número de item definido na lista de materiais ou na fórmula para a ordem de produção selecionada ou a ordem do lote.
-   O material pode ser consumido em excesso. Por exemplo, se for estimado que o material será consumido com a quantidade de 100 libras, então pode ser consumido em excesso com uma quantidade de, por exemplo, 105 libras.




[!INCLUDE[footer-include](../../includes/footer-banner.md)]