--- 
title: "Carregar configurações para relatórios eletrônicos no Lifecycle Services"
description: "As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma nova configuração do Relatório eletrônico (RE) e carregá-la ao Microsoft Lifecycle Services (LCS)."
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
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 6aa6bf7e08285d18210741ba6618878955009280
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2018

---
# <a name="upload-electronic-reporting-configurations-into-lifecycle-services"></a>Carregar configurações para relatórios eletrônicos no Lifecycle Services

[!include [task guide banner](../../includes/task-guide-banner.md)]

As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma nova configuração do Relatório eletrônico (RE) e carregá-la ao Microsoft Lifecycle Services (LCS).

Neste exemplo, você criará e carregará uma configuração para o LCS (Lifecycle Services) da empresa de exemplo, Litware, Inc. Estas etapas podem ser executadas em qualquer empresa, uma vez que as configurações ER são compartilhadas entre todas as empresas. Para completar essas etapas, você deve primeiro completar as etapas do procedimento “Criar um provedor de configuração e marcá-lo como ativo“. O acesso ao LCS também é necessário para a conclusão dessas etapas.

1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
2. Selecione 'Litware, Inc.' e defina-a como ativa.
3. Clique em Configurações.

## <a name="create-a-new-data-model-configuration"></a>Criar uma nova configuração de modelo de dados
1. Clique em Criar configuração para abrir a caixa de diálogo suspensa.
    * Você irá criar uma configuração que contém um modelo de dados de exemplo para documentos eletrônicos. Esta configuração do modelo de dados será carregada no LCS posteriormente.  
2. No campo Nome, digite "Configuração de modelo de exemplo".
    * Configuração do modelo de exemplo  
3. No campo Descrição, digite 'Configuração do modelo de exemplo'.
    * Configuração do modelo de exemplo  
4. Clique em Criar configuração.
5. Clique em Designer de modelo.
6. Clique em Novo.
7. No campo Nome, digite "Ponto de entrada".
    * Ponto de entrada  
8. Clique em Adicionar.
9. Clique em Salvar.
10. Feche a página.
11. Clique em Alterar status.
12. Clique em Concluir.
13. Clique em OK.

## <a name="register-a-new--repository"></a>Registrar um novo repositório
1. Feche a página.
2. Clique em Repositórios.
    * Isso permite que você abra a lista de repositórios para o provedor de configuração da Litware, Inc.  
3. Clique em Adicionar para abrir a caixa de diálogo suspensa.
    * Isso permite que você adicione um novo armazenamento.  
4. No campo Tipo de configuração do repositório, selecione LCS.
5. Clique em Criar repositório.
6. No campo Projeto, insira ou selecione um valor.
    * Selecione o projeto LCS desejado. Você deve ter acesso ao projeto.  
7. Clique em OK.
    * Concluir uma nova entrada de armazenamento.  
8. Na lista, marque a linha selecionada.
    * Selecionar o registro de repositório LCS.  
    * Observe que uma loja registrada está marcada por importância atual do fornecedor que as únicas configurações de propriedade do fornecedor podem ser colocadas para esta loja e, consequentemente, ser cobradas no projeto selecionado de LCS.  
9. Clique em Abrir.
    * Abra o armazenamento para exibir a lista de configurações de ER. Ficará vazio se o projeto ainda não foi usado para compartilhamento das configurações de ER.  
10. Feche a página.
11. Feche a página.

## <a name="upload-configuration-into-lcs"></a>Carregar configuração para o LCS
1. Clique em Configurações.
2. Na árvore, selecione "Configuração do modelo de exemplo".
    * Selecione uma configuração criada que já esteja concluída.  
3. Na lista, localize e selecione o PDV desejado.
    * Selecione a versão da configuração selecionada com o status de "Concluído".  
4. Clique em Alterar status.
5. Clique em Compartilhar.
    * O status da configuração será alterado de "Concluído" para "Compartilhado" quando for publicado no LCS.  
6. Clique em OK.
7. Na lista, localize e selecione o PDV desejado.
    * Selecione a versão da configuração com o status de "Compartilhado".  
    * Observe que o status da versão selecionada foi alterado de "Concluído" para "Compartilhado".  
8. Feche a página.
9. Clique em Repositórios.
    * Isso permite que você abra a lista de repositórios para o provedor de configuração da Litware, Inc.  
10. Clique em Abrir.
    * Selecione a loja de LCS e a abra.  
    * Observe que a configuração selecionada será mostrada como um ativo do projeto selecionado de LCS.  
    * Abra LCS usando https://lcs.dynamics.com. Abra um projeto que tenha sido usado anteriormente para registro do repositório, abra a "Biblioteca de ativo" deste projeto, e expanda o conteúdo do tipo de ativo "Configuração GER"! - a configuração ER carregada estará disponível. Observe que a configuração do LCS carregada pode ser importada para outra instância do Microsoft Dynamics 365 for Finance and Operations, se os fornecedores tiverem acesso a este projeto do LCS.  


