--- 
title: "Importar uma configuração do Lifecycle Services para relatório eletrônico (ER)"
description: "As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode importar uma nova versão de uma configuração do Relatório eletrônico (RE) do Microsoft Lifecycle Services (LCS)."
author: NickSelin
manager: AnnBe
ms.date: 05/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 9eb4f54897c84b98828c927f0f93613583fd4599
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="import-a-configuration-from-lifecycle-services-for-electronic-reporting-er"></a>Importar uma configuração do Lifecycle Services para relatório eletrônico (ER)

[!include [task guide banner](../../includes/task-guide-banner.md)]

As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode importar uma nova versão de uma configuração do Relatório eletrônico (RE) do Microsoft Lifecycle Services (LCS).

Neste exemplo, você selecionará a versão desejada da configuração de ER e a importará para a empresa de exemplo, Litware, Inc. Essas etapas podem ser executadas em qualquer empresa, uma vez que as configurações de ER são compartilhadas entre as empresas. Para completar essas etapas, você deve primeiro completar as etapas do procedimento "Carregar uma configuração de ER no Lifecycle Services". O acesso ao LCS também é necessário para a conclusão dessas etapas.

1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
2. Clique em Configurações.

## <a name="delete-a-shared-version-of-data-model-configuration"></a>Excluir uma versão compartilhada de configuração do modelo de dados
1. Na árvore, selecione "Configuração do modelo de exemplo".
    * A primeira versão de uma configuração do modelo de dados de amostra foi criada e publicada ao LCS durante o procedimento "Carregamento de uma configuração ER em um Lifecycle Services. Nesse procedimento, você excluirá esta versão da configuração de ER. Esta versão de configuração do modelo de dados de amostra será importada posteriormente do LCS.  
2. Na lista, localize e selecione o PDV desejado.
    * Selecione a versão dessa configuração que tem um status "Compartilhado". Este status indica que a configuração esteve publicada ao LCS.  
3. Clique em Alterar status.
4. Clique em Descontinuar.
    * Altere o status da versão selecionada de "Compartilhado" para "Interrompido" para tornar a exclusão disponível.  
5. Clique em OK.
6. Na lista, localize e selecione o PDV desejado.
    * Selecione a versão dessa configuração que tem um status "Interrompido".  
7. Clique em Excluir.
8. Clique em Sim.
    * Observe que somente a versão de rascunho 2 da configuração selecionada do modelo de dados está disponível.  
9. Feche a página.

## <a name="import-a-shared-version-of-data-model-configuration-from-lcs"></a>Importar uma versão compartilhada de configuração do modelo de dados do LCS
1. Na lista, marque a linha selecionada.
    * Abra a lista de repositórios para a 'Litware, Inc.'. provedor de configuração.  
2. Clique em Repositórios.
3. Clique em Abrir.
    * Selecione a loja de LCS e a abra.  
4. Na lista, marque a linha selecionada.
    * Selecione a primeira versão da "Configuração de modelo de exemplo" na lista de versões.  
5. Clique em Importar.
6. Clique em Sim.
    * Confirme a importação da versão selecionada de LCS.  
    * Observe que a mensagem informativa (acima do formulário) confirma a conclusão bem-sucedida de importação da versão selecionada.  
7. Feche a página.
8. Feche a página.
9. Clique em Configurações.
10. Na árvore, selecione "Configuração do modelo de exemplo".
11. Na lista, localize e selecione o PDV desejado.
    * Selecione a versão dessa configuração que tem um status "Compartilhado".  
    * Observe que versão 1 compartilhada da configuração do modelo de dados selecionada agora também está disponível.  


