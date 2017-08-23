--- 
title: "Configurar um item de menu de dispositivo móvel para executar trabalhos em uma ordem de compra"
description: "Este procedimento mostra como estabelecer um item de menu do dispositivo móvel."
author: BibiSp
manager: AnnBe
ms.date: 08/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bibis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 7ce132b590fffb753948e663763b8f3ef576ac36
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-a-mobile-device-menu-item-for-completing-work-in-a-purchase-order"></a>Configurar um item de menu de dispositivo móvel para executar trabalhos em uma ordem de compra

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como estabelecer um item de menu do dispositivo móvel. Neste exemplo, o item de menu é usado para realizar trabalho do tipo Ordem de compra. A classe de trabalho associada ao item de menu determina qual trabalho é válido. Você pode usar este guia na empresa USMF de dados de demonstração. Esse procedimento geralmente é realizado por um gerente de depósito.


## <a name="create-a-mobile-device-menu-item"></a>Criar um item de menu de dispositivo móvel
1. Vá para Itens de menu do dispositivo móvel.
2. Clique em Novo.
3. No campo Item de menu, digite um valor.
    * Inserir um valor único. Por exemplo, você poderia digitar POMove. Lembre-se do valor, você precisará dele mais tarde.  
4. No campo Título, digite um valor.
    * Este é o título que será exibido no dispositivo móvel. Por exemplo, você poderia digitar PO Move.  
5. No campo Modo, selecione 'Trabalho'.
6. Selecione Sim no campo Usar trabalho existente.
    * Este item de menu do dispositivo móvel é usado para realizar o trabalho existente. Portanto, você deve definir esse valor para Sim.  
    * O campo de status de estoque de vídeo determina se será exibido o status de inventário do estoque disponível para o trabalhador de depósito no dispositivo móvel.  
7. No campo Direcionado por, selecione 'Agrupamento do sistema'.
    * Quando você seleciona algo no campo Direcionado, os campos adicionais aparecem na seção geral nesta página. Os campos que aparecem dependem do que você selecionou. Quando você seleciona o Sistema de agrupamento dois novos campos são adicionados. Eles são explicados abaixo.  
8. No campo Agrupamento do sistema, selecione 'WorkPoolId'.
    * Quando os funcionários do depósito abrirem este item de menu, serão solicitados para fazer a varredura de uma identificação do grupo de trabalho. Todas as ordens com esta ID de grupo de trabalho abrem as linhas do pedido de trabalho com uma das classes de trabalho para este item de menu que serão enviadas para o usuário.  
9. No campo Etiqueta de agrupamento do sistema, digite um valor.
    * Este é o texto exibido para o usuário no dispositivo móvel. Por exemplo, você poderia digitar Pool de trabalho.  
10. Selecione Sim no campo Substituir placa de licença durante a colocação.
    * Esta opção permite que os funcionários do depósito substituam a placa de destino quando os itens são colocados para baixo em um local de matrícula controlado.  
11. Selecione Sim no campo Armazenamento de grupo.
    * Se todas as linhas na ordem do trabalho compartilham o mesmo local, o usuário receberá uma instrução Put combinada para todas as linhas.  
    * ID do modelo de auditoria: um modelo de auditoria de trabalho permite que você especifique o processo de trabalho para um item de menu que deve ser interrompido para que outra operação possa ser executada. Por exemplo, se esse item de menu for para o trabalho de entrada, o modelo de auditoria poderá exigir que o trabalhador verifique a temperatura. O ponto em que o processo for interrompido será especificado no modelo de auditoria e poderá ser, por exemplo, quando o trabalho for iniciado ou concluído, ou quando seu status for alterado.  
12. Expanda a seção Classes de trabalho.
13. Clique em Novo.
14. No campo ID de classe de trabalho, digite 'Compra'.
    * O pool de trabalho restringe o trabalho para o qual o item de menu pode ser usado. Nesse caso, ele será usado para linhas de ordem de trabalho abertas com a ID de classe de trabalho de compra.  
15. Clique em Salvar.

## <a name="set-up-work-confirmation"></a>Configurar confirmação de trabalho
1. Clique em Configuração de confirmação de trabalho.
2. No campo Tipo de trabalho, selecione 'Separar'.
3. Marque a caixa de seleção Confirmação automática.
    * A instrução de trabalho com a escolha do tipo de trabalho será confirmada automaticamente. Esta instrução não será apresentada ao usuário.  
4. Clique em Novo.
5. No campo Tipo de trabalho, selecione 'Colocar'.
6. Marque a caixa de seleção Confirmação de localização.
    * O trabalhador de depósito será solicitado a executar uma verificação de confirmação do local, quando o item for colocado para baixo.  
7. Clique em Salvar.
8. Feche a página.
9. Feche a página.

## <a name="add-the-menu-item-to-a-mobile-device-menu"></a>Adicionar o item de menu ao menu de um dispositivo móvel
1. Vá para Menu de dispositivos móveis.
2. Clique em Editar.
3. Use o Filtro Rápido para localizar registros. Por exemplo, filtre no campo Nome com um valor de 'entrada'.
    * Você deseja localizar o menu que você usa para itens de menu de entrada. No USMF isto é chamado de Entrada.  
4. Na árvore, selecione 'um valor'.
5. Clique na seta que aponta para a direita.
6. Clique em Salvar.
7. Feche a página.


