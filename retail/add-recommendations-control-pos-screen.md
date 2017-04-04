---
title: "Adicionar um controle das recomendações para a página de transação em um dispositivo POS"
description: "Este tópico descreve como adicionar um controle das recomendações na tela de transação em um dispositivo (POS) do ponto de venda usando o designer do layout de tela no Microsoft Dynamics 365 para as operações."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 2377b1639a3c95fe6bba4754c4069cc12043e3d3
ms.lasthandoff: 03/31/2017


---

# <a name="add-a-recommendations-control-to-the-transaction-page-on-a-pos-device"></a>Adicionar um controle das recomendações para a página de transação em um dispositivo POS

Este tópico descreve como adicionar um controle das recomendações na tela de transação em um dispositivo (POS) do ponto de venda usando o designer do layout de tela no Microsoft Dynamics 365 para as operações.

Você pode exibir recomendações do dispositivo no POS quando você usa o Microsoft Dynamics 365 para as operações. o é *Recommendations* itens que o cliente pode ser baseado interessado no histórico de compra, em itens da lista de objetivos pretendidos, e em itens que compraram online outros clientes e em lojas físicas. Para exibir recomendações de produto, é necessário adicionar um controle na tela de transação usando o designer do layout da tela.

## <a name="open-layout-designer"></a>Designer do layout
1.  Ir ** varejo e comércio ** &gt; ** a configuração de canal ** &gt; ** configuração POS ** &gt; ** PDV ** &gt; ** layouts de tela **.
2.  Use o filtro para localizar rapidamente a tela a qual deseja adicionar o controle. Por exemplo, filtre o ** ID do layout da tela ** campo usando um valor “F2CP16: 9M”.
3.  Na lista, localize e selecione o registro desejado. Por exemplo, selecione o nome “: F2CP16: ID do layout da tela de 9M: F2CP16: 9M”.
4.  Clique ** ** designer do layout.
5.  Rastrear os avisos para iniciar o designer do layout. Quando solicitado, insira credenciais para as mesmas credenciais que estavam em uso quando o designer do layout foi iniciado ** layouts de tela ** de página.
6.  Quando você inserir uma página, semelhante ao seguir é exibido. O layout será diferente dependendo as personalizações feitas para o armazenamento.

[![(screenlayout-pic-1]. /media/screenlayout-pic-1.png)](. /media/screenlayout-pic-1.png) Escolhem uma opção de exibição
-----------------------

Há duas opções de configuração disponíveis. Escolha a opção que funciona melhor do repositório, rastrear e instruções restante para concluir configurar o controle. As duas opções são:
-   As recomendações é sempre visível.
-   ** A recomendações ** guia aparece na grade ao lado direito da tela.

#### <a name="to-make-recommendations-always-visible"></a>Para fazer recomendações sempre visível

1.  Reduzir à altura das linhas de detalhes da transação de forma que esteja a altura que o painel do cliente à esquerda. []. (/media/pic-2.png) [![(screenlayout-pic-2]. /media/screenlayout-pic-2.png)](. /media/screenlayout-pic-2.png)
2.  Menu da esquerda, o arrastar e solta o controle das recomendações entre a linha área detalhes e a parte inferior de transação da grade de botões no centro de tela de transação. Redimensione a controle isso que cabem no espaço. []. (/media/pic-3.png) [![(screenlayout-pic-3]. /media/screenlayout-pic-3.png)](. /media/screenlayout-pic-3.png)
3.  ** Clicam X ** para salvar e sair do designer do layout.
4.  Em dynamics 365 para operações, vai ** varejo e comércio ** &gt; ** o varejista TI ** &gt; ** agendas ** de distribuição.
5.  Na lista, selecione ** ** 1090 registros.
6.  Clique ** execução ** agora.

#### <a name="to-add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a>Para adicionar uma guia das recomendações para a grade de botões no lado direito da tela

1.  Clique com o botão direito no espaço vazio na guia do último a grade de botões localizado no lado direito da página.
2.  Clique ** personalizar **. [![(pic-5]. /media/pic-5.png)](. /media/pic-5.png)
3.  Clique ** novo ** guia.
4.  Localizar o novo guia que você adicionou apenas. Você também precise rolar para baixo.
5.  ** Conteúdos ** no suspenso, selecione ** produtos recomendados **. [![(pic-6]. /media/pic-6.png)](. /media/pic-6.png)
6.  ** Rótulo ** no campo, digite um nome para a guia das recomendações. Por exemplo, tipo “recomendados produtos”.
7.  ** ** Imagem no campo, selecione a imagem para exibir na guia.
8.  Click **OK**. O novo guia aparece na grade de botões.
9.  ** Clicam X ** para salvar e sair do designer do layout.
10. Em dynamics 365 para operações, vai ** varejo e comércio ** &gt; ** o varejista TI ** &gt; ** agendas ** de distribuição.
11. Na lista, selecione ** ** 1090 registros.
12. Clique ** execução ** agora.


<a name="see-also"></a>Consulte também
--------

[] Personalizado visão geral das recomendações de produto (personalized-product-recommendations.md)


