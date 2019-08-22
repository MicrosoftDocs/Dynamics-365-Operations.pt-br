---
title: Configurar um item de menu do dispositivo móvel para registrar itens recebidos
description: Esta tarefa tem como foco a configuração de um item de menu de dispositivo móvel.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem, WHSRFMenu
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bd6c40324555ae16de3192c91cf64d03d44b5ad4
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1847126"
---
# <a name="set-up-a-mobile-device-menu-item-to-register-received-items"></a>Configurar um item de menu do dispositivo móvel para registrar itens recebidos

[!include [task guide banner](../../includes/task-guide-banner.md)]

Esta tarefa tem como foco a configuração de um item de menu de dispositivo móvel. Esse item de menu é usado para registro do recibo de itens encomendados por meio de ordens de compra. 

Você pode usar este guia na empresa USMF de dados de demonstração. Esse procedimento é destinado ao gerente do depósito.


## <a name="create-a-mobile-device-menu-item"></a>Criar um item de menu de dispositivo móvel
1. Vá para Gerenciamento de depósito > Configuração > Dispositivo móvel > Itens de menu de dispositivo móvel.
2. Clique em Novo.
3. No campo Item de menu, digite um valor.
    * Este é o único identificador para esse item de menu de dispositivo móvel. Por exemplo, você poderia registrar 'Registro da minha OC'.  
4. No campo Título, digite um valor.
    * Este é o título que será exibido para o usuário no dispositivo móvel. Por exemplo, você poderia registrar 'Registro da OC'.  
5. No campo Modo, selecione 'Trabalho'.
    * O registro de quantidades disponíveis recebidas para uma linha de ordem de compra criará trabalho para mover itens da área de recebimento para o estoque. O trabalho não é criado até que os itens estejam registrados.  Portanto, deixe a opção Usar trabalho existente definida como Não.  
6. Expandir ou recolher a seção Geral.
7. No campo Criação de trabalho, selecione 'Recebimento do item da ordem de compra'.
    * Uma linha de ordem de compra que só deve ser identificada antes de estar disponível pode ser registrada no depósito. Nesse cenário, o dispositivo móvel registrará o número da ordem de compra e o número do item, o que permitirá ao sistema identificar a linha da OC. O trabalho de armazenamento será criado e pode ser separado por outro trabalhador.    O método de criação de trabalho selecionado determina que campos se tornam disponíveis na guia rápida Geral.  
    * Se selecionar a opção Usar dados padrão, o botão Dados padrão será habilitado. Aqui você pode selecionar campos para exibir os dados que um trabalhador geralmente precisa em seu trabalho diário para que esses valores sejam mostrados no dispositivo móvel.  
    * O parâmetro de agrupamento Placa de licença funciona em combinação com o grupo de sequências de unidade atribuído ao item sendo recebido. Você pode especificar se os recebimentos menores ou maiores que um palete devem ser agrupados em uma placa de licença ou divididos em uma placa de licença separada para cada unidade.  
    * Selecionar a opção Gerar placa de licença criará um número de placa de licença exclusivo baseado na seleção de sequência numérica.   
    * Você pode selecionar o modelo que será usado quanto o trabalho for criado. Por exemplo, se você registrar um item para uma ordem de compra, o trabalho de armazenamento será gerado com base no modelo de trabalho. Se não selecionar um modelo de trabalho aqui, o sistema atribuirá um modelo baseado nos critérios de consulta que estão associados aos modelos.  
    * Se códigos de disposição forem exibidos no dispositivo móvel, os trabalhadores poderão avaliar o status ou a qualidade dos itens e selecionar o código apropriado. As regras para o código de disposição determinam se os itens estarão disponíveis para outros processos do depósito. As regras também determinam qual diretiva de localização é usada para o trabalho que foi criado.   
    * Se selecionar a opção Códigos de disposição em lotes, os trabalhadores poderão avaliar o status ou a qualidade de um lote e selecionar o código de disposição apropriado.  As regras definidas no código de disposição de lote determinam se o lote estará disponível para outros processos do depósito.  
    * Se você selecionar a opção Imprimir etiquetas, uma etiqueta de placa de licença será impressa automaticamente quando itens forem recebidos.  
8. Clique em Salvar.
9. Feche a página.

## <a name="add-the-menu-item-to-a-mobile-device-menu"></a>Adicionar o item de menu ao menu de um dispositivo móvel
1. Vá para Gerenciamento de depósito > Configuração > Dispositivo móvel > Menu de dispositivo móvel.
2. Use o Filtro Rápido para filtrar no campo Nome com um valor de 'entrada'.
3. Clique em Editar.
4. Na árvore, selecione 'Na árvore do menu disponível e de itens, selecione o item de menu que você criou antes'.
    * Selecione o item de menu que você criou antes.  
5. Clique na seta que aponta para a direita.
6. Clique em Salvar.
7. Feche a página.

