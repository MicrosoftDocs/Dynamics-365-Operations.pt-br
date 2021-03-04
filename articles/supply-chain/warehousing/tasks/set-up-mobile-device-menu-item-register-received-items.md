---
title: Configurar um item de menu do dispositivo móvel para registrar itens recebidos
description: Este tópico tem como foco a configuração de um item de menu de dispositivo móvel.
author: ShylaThompson
manager: tfehr
ms.date: 08/16/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem, WHSRFMenu, WHSRFDefaultData
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f636a1f3d598a069c3922160eedbe05b68bc91eb
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4422539"
---
# <a name="set-up-a-mobile-device-menu-item-to-register-received-items"></a>Configurar um item de menu do dispositivo móvel para registrar itens recebidos

[!include [banner](../../includes/banner.md)]

Este tópico tem como foco a configuração de um item de menu de dispositivo móvel. Esse item de menu é usado para registro do recibo de itens encomendados por meio de ordens de compra. 

Você pode usar este guia na empresa USMF de dados de demonstração. Esse procedimento é destinado ao gerente do depósito.


## <a name="create-a-mobile-device-menu-item"></a>Criar um item de menu de dispositivo móvel
1. No painel de navegação, acesse **Módulos > Gerenciamento de depósito > Configuração > Dispositivo móvel > Itens de menu de dispositivo móvel**.
2. Selecione **Novo**.
3. No campo **Nome do item de menu**, digite um valor. Este é o único identificador para esse item de menu de dispositivo móvel. Por exemplo, você poderia digitar `My PO registration`.  
4. No campo **Título**, digite um valor. Este é o título que será exibido para o usuário no dispositivo móvel. Por exemplo, você poderia digitar `PO registration`.  
5. No campo **Modo**, selecione **Trabalho**. O registro de quantidades disponíveis recebidas para uma linha de ordem de compra criará trabalho para mover itens da área de recebimento para o estoque. O trabalho não é criado até que os itens estejam registrados. Portanto, deixe a opção **Usar trabalho existente** definida como **Não**.
6. No campo **Criação de trabalho**, da seção **Geral**, selecione **Recebimento do item da ordem de compra**.
    - Uma linha de ordem de compra que só deve ser identificada antes de estar disponível pode ser registrada no depósito. Nesse cenário, o dispositivo móvel registrará o número da ordem de compra e o número do item, o que permitirá ao sistema identificar a linha da OC. O trabalho de armazenamento será criado e pode ser separado por outro trabalhador. O método de criação de trabalho selecionado determina que campos se tornam disponíveis na Guia Rápida **Geral**.  
    - Se selecionar a opção **Usar dados padrão**, o botão **Dados padrão** será habilitado. Aqui você pode selecionar campos para exibir os dados que um trabalhador geralmente precisa em seu trabalho diário para que esses valores sejam mostrados no dispositivo móvel.  
    - O parâmetro de agrupamento **Placa de licença** funciona em combinação com o grupo de sequências de unidade atribuído ao item sendo recebido. Você pode especificar se os recebimentos menores ou maiores que um palete devem ser agrupados em uma placa de licença ou divididos em uma placa de licença separada para cada unidade.  
    - Selecionar a opção **Gerar placa de licença** criará um número de placa de licença exclusivo baseado na seleção de sequência numérica.  
    - Você pode selecionar o modelo que será usado quanto o trabalho for criado. Por exemplo, se você registrar um item para uma ordem de compra, o trabalho de armazenamento será gerado com base no modelo de trabalho. Se não selecionar um modelo de trabalho aqui, o sistema atribuirá um modelo baseado nos critérios de consulta que estão associados aos modelos.  
    - Se códigos de disposição forem exibidos no dispositivo móvel, os trabalhadores poderão avaliar o status ou a qualidade dos itens e selecionar o código apropriado. As regras para o código de disposição determinam se os itens estarão disponíveis para outros processos do depósito. As regras também determinam qual diretiva de localização é usada para o trabalho que foi criado.   
    - Se selecionar a opção **Códigos de disposição em lotes**, os trabalhadores poderão avaliar o status ou a qualidade de um lote e selecionar o código de disposição apropriado. As regras definidas no código de disposição de lote determinam se o lote estará disponível para outros processos do depósito.  
    - Se você selecionar a opção **Imprimir etiquetas**, uma etiqueta de placa de licença será impressa automaticamente quando itens forem recebidos.  
7. Selecione **Salvar**.
8. Feche a página.

## <a name="add-the-menu-item-to-a-mobile-device-menu"></a>Adicionar o item de menu ao menu de um dispositivo móvel
1. No painel de navegação, acesse **Módulos > Gerenciamento de depósito > Configuração > Dispositivo móvel > Menu de dispositivo móvel**.
2. Use o **Filtro Rápido** para filtrar o campo **Nome** com o valor `inbound`.
3. Selecione **Editar**.
4. Na árvore dos Menu disponíveis e de itens, selecione o item de menu que você criou antes.
5. Selecione a seta que aponta para a direita.
6. Selecione **Salvar**.
7. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]