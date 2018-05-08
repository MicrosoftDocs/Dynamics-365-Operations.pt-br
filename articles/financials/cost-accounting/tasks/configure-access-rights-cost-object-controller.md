--- 
title: Configurar direitos de acesso para um controlador de objeto de custo
description: Use este procedimento para configurar direitos de acesso para um controlador de objeto de custo.
author: YuyuScheller
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b0647e1ec55d23607d07f38105e42af498ad1174
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="configure-access-rights-for-a-cost-object-controller"></a>Configurar direitos de acesso para um controlador de objeto de custo

[!include [task guide banner](../../includes/task-guide-banner.md)]

Use este procedimento para configurar direitos de acesso para um controlador de objeto de custo. Esta gravação usa os dados da empresa de demonstração USP2.


## <a name="assign-the-cost-object-controller-role"></a>Atribuir a função de controlador de objeto de custo
1. Vá para Administração do sistema > Usuários > Usuários.
2. Use o Filtro Rápido para localizar registros. Por exemplo, filtre no campo Nome de usuário um valor de "alicia".
3. Na lista, clique no link na linha selecionada.
4. Clique em Atribuir funções.
5. Na lista, localize e selecione o PDV desejado.
6. Clique em OK.

## <a name="enable-access-list-security"></a>Habilitar segurança da lista de acesso
1. Vá para Contabilização de custos > Dimensões > Hierarquias de dimensões.
2. Na lista, localize e selecione o PDV desejado.
    * Selecione Organização.  
3. Clique em Editar.
4. Selecione Sim no campo Acessar hierarquia de lista.
5. Clique em Exibir hierarquia.

## <a name="assign-access-rights-to-user"></a>Atribuir direitos de acesso ao usuário
1. Clique em Novo.
2. Na lista, marque a linha selecionada.
3. No campo ID do usuário, insira ou selecione um valor.
    * Selecione Administrador.  
4. Na árvore, selecione 'Organização\CEO\CFO\FIM'.
5. Clique em Novo.
6. Na lista, marque a linha selecionada.
7. No campo ID do usuário, insira ou selecione um valor.
    * Selecione Alicia.  
8. Clique em Salvar.

## <a name="enable-access-rights-in-cost-accounting"></a>Habilitar direitos de acesso na Contabilização de custos
1. Vá para Contabilização de custos > Configuração > Parâmetros.
2. Clique na guia Geral.
3. Selecione Sim no campo Habilitar acesso de visualização para membros de dimensão de objeto de custo.
4. Clique em Salvar.
5. Feche a página.
6. Vá para Contabilização de custos > Configuração > Configuração de espaço de trabalho de controle de custo.
7. Clique em Editar.
8. Selecione Sim no campo Publicado.
    * Se selecionar Sim, um usuário atribuído a uma das quatro funções poderá consultar os relatórios no espaço de trabalho de controle de custo: gerente de contabilidade de custo, contador de custos, funcionário de contador de custo e controlador de objeto de custo. Se selecionar Não, somente um usuário atribuído a uma das quatro funções poderá consultar os relatórios: gerente de contabilidade de custo, contador de custos e funcionário do contador de custos.    
9. Clique em Salvar.


