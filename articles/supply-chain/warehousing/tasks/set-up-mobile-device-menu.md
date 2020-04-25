---
title: Configurar um item de menu do dispositivo móvel para concluir o trabalho do tipo Ordem de compra
description: Este tópico mostra como estabelecer um item de menu do dispositivo móvel.
author: ShylaThompson
manager: tfehr
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem, WHSRFAutoConfirm, WHSRFMenu
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 905094ae4e76fadbebea1892ec20427f32e3e71d
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3216807"
---
# <a name="set-up-a-mobile-device-menu-item-for-completing-work-of-type-purchase-order"></a>Configurar um item de menu do dispositivo móvel para concluir o trabalho do tipo Ordem de compra

[!include [banner](../../includes/banner.md)]

Este tópico mostra como estabelecer um item de menu do dispositivo móvel. Neste exemplo, o item de menu é usado para realizar trabalho do tipo Ordem de compra. A classe de trabalho associada ao item de menu determina qual trabalho é válido. Você pode usar este guia na empresa USMF de dados de demonstração. Esse procedimento geralmente é realizado por um gerente de depósito.


## <a name="create-a-mobile-device-menu-item"></a>Criar um item de menu de dispositivo móvel
1. Acesse **Itens de menu do dispositivo móvel** inserindo-o na barra de navegação.
2. Selecione **Novo**.
3. No campo **Nome do item de menu**, digite um valor. Inserir um valor único. Por exemplo, você poderia digitar `POMove`. Lembre-se do valor, você precisará dele mais tarde.  
4. No campo **Título**, digite um valor. Este é o título que será exibido no dispositivo móvel. Por exemplo, você poderia digitar `PO Move`.  
5. No campo **Modo**, selecione **Trabalho**.
6. Selecione **Sim** no campo **Usar trabalho existente**.
    - Este item de menu do dispositivo móvel é usado para realizar o trabalho existente. Portanto, você deve definir esse valor como **Sim**.  
    - O campo de **Status de estoque de vídeo** determina se será exibido o status de inventário do estoque disponível para o trabalhador de depósito no dispositivo móvel.  
7. No campo **Direcionado por**, selecione **Agrupamento do sistema**. Quando você seleciona algo no campo **Direcionado**, os campos adicionais aparecem na seção **Geral** nesta página. Os campos que aparecem dependem do que você selecionou. Quando você seleciona o **Sistema de agrupamento**. dois novos campos são adicionados. Eles são explicados abaixo.  
8. No campo **Agrupamento do sistema**, selecione **WorkPoolId**. Quando os funcionários do depósito abrirem este item de menu, serão solicitados para fazer a varredura de uma identificação do grupo de trabalho. Todas as ordens com esta ID de grupo de trabalho abrem as linhas do pedido de trabalho com uma das classes de trabalho para este item de menu que serão enviadas para o usuário.  
9. No campo **Etiqueta de agrupamento do sistema**, digite um valor. Este é o texto exibido para o usuário no dispositivo móvel. Por exemplo, você poderia digitar **Pool de trabalho**.  
10. Selecione **Sim** no campo **Substituir placa de licença durante a colocação**. Esta opção permite que os funcionários do depósito substituam a placa de destino quando os itens são colocados para baixo em um local de matrícula controlado.  
11. Selecione **Sim** no campo **Armazenamento de grupo**.
    - Se todas as linhas na ordem do trabalho compartilham o mesmo local, o usuário receberá uma instrução Put combinada para todas as linhas. 
    - ID do modelo de auditoria: um modelo de auditoria de trabalho permite que você especifique o processo de trabalho para um item de menu que deve ser interrompido para que outra operação possa ser executada. Por exemplo, se esse item de menu for para o trabalho de entrada, o modelo de auditoria poderá exigir que o trabalhador verifique a temperatura. O ponto em que o processo for interrompido será especificado no modelo de auditoria e poderá ser, por exemplo, quando o trabalho for iniciado ou concluído, ou quando seu status for alterado.  
12. Expanda a seção **Classes de trabalho**.
13. Selecione **Novo**.
14. No campo **ID de classe de trabalho**, digite `Purchase`. O pool de trabalho restringe o trabalho para o qual o item de menu pode ser usado. Nesse caso, ele será usado para linhas de ordem de trabalho abertas com a ID de classe de trabalho de compra.  
15. Selecione **Salvar**.

## <a name="set-up-work-confirmation"></a>Configurar confirmação de trabalho
1. Selecione **Configuração de confirmação de trabalho**.
2. No campo **Tipo de trabalho**, selecione **Separar**.
3. Marque a caixa de seleção **Confirmação automática**. A instrução de trabalho com a escolha do tipo de trabalho será confirmada automaticamente. Esta instrução não será apresentada ao usuário.  
4. Selecione **Novo**.
5. No campo **Tipo de trabalho**, selecione 'Colocar'.
6. Marque a caixa de seleção **Confirmação de localização**. O trabalhador de depósito será solicitado a executar uma verificação de confirmação do local, quando o item for colocado para baixo.  
7. Selecione **Salvar**.

## <a name="add-the-menu-item-to-a-mobile-device-menu"></a>Adicionar o item de menu ao menu de um dispositivo móvel
1. Acesse o menu **Dispositivo móvel** inserindo-o na barra de navegação.
2. Selecione **Editar**.
3. Use o Filtro Rápido para localizar registros. Por exemplo, filtre no campo **Nome** com um valor de **entrada**. Você deseja localizar o menu que você usa para itens de menu de entrada. No USMF isto é chamado de **Entrada**.  
4. Na árvore, selecione **um valor**.
5. Selecione a seta que aponta para a direita.
6. Selecione **Salvar**.
7. Feche a página.
