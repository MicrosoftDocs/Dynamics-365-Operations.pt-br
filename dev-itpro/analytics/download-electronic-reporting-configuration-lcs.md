---
title: "Baixar configurações do Relatório eletrônico no Lifecycle Services"
description: "Este tópico explica como o download configurações relatando eletrônicas (ER) de serviços (LCS) do Microsoft Dynamics lifecycle."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ERSolutionImport, ERWorkspace
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 9dca5dec846670da25926826f59d7bce0fa0dcea
ms.lasthandoff: 03/31/2017


---

# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a>Baixar configurações do Relatório eletrônico no Lifecycle Services

Este tópico explica como o download configurações relatando eletrônicas (ER) de serviços (LCS) do Microsoft Dynamics lifecycle.

Este tutorial conduz você pelo processo de download da versão mais recente das configurações do ER (Relatório eletrônico) do Microsoft Dynamics LCS (Lifecycle Services).

1.  Entre no Dynamics 365 for Operations usando uma das seguintes funções:
    -   Desenvolvedor de relatório eletrônico
    -   Consultor funcional de relatório eletrônico
    -   Administrador do sistema

2.  Ir ** administração organizacional ** &gt; ** o relatório eletrônico **.
3.  Na seção **Provedores de configuração**, selecione o bloco **Microsoft**.
4.  No bloco **Microsoft**, clique em **Repositórios**. [atualização-er--lcs-para-Senhora-aberto-Senhora-repositório- lista![(]. /media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](. /media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)
5.  Na página **Repositórios de configuração**, na grade, selecione o repositório existente do tipo **LCS**. Se esse repositório não aparecer na grade, siga estas etapas:
    1.  Clique em **Adicionar** para adicionar um novo repositório.
    2.  Selecione **LCS** como tipo de repositório.
    3.  Clique em **Criar repositório**.
    4.  Insira um nome e uma descrição para o repositório.
    5.  Clique em **OK** para confirmar a nova entrada do repositório.
    6.  Na grade, selecione o novo repositório do tipo **LCS**.

6.  Clique em **Abrir** para exibir a lista de configurações de ER para o repositório selecionado. [atualização-er--lcs-para-Senhora-fazer-lcs- repositório![(]. /media/update-er-from-lcs-for-ms-make-lcs-repository.png)](. /media/update-er-from-lcs-for-ms-make-lcs-repository.png)
7.  Na árvore de configurações, no painel esquerdo, selecione a configuração de ER necessária.
8.  Na Guia Rápida **Versões**, selecione a versão necessária da configuração de ER selecionada.
9.  Clique em **Importar** para baixar a versão selecionada do LCS para a instância atual do Dynamics 365 for Operations. **Observação:** o botão **Importar** não está disponível para as versões de configuração do ER que já estão presentes na instância do Dynamics 365 for Operations. [atualização-er--lcs-para-Senhora-download- configuração do![(]. /media/update-er-from-lcs-for-ms-download-configuration.png)](. /media/update-er-from-lcs-for-ms-download-configuration.png)

**Observação:** dependendo das configurações de ER, as configurações são validadas depois que são importadas. Talvez você seja notificado sobre problemas de inconsistências descobertos. Você deve resolver esses problemas para que possa usar a versão de configuração importada. Para obter mais informações, consulte a lista de itens relacionados para este tópico.

<a name="see-also"></a>Consulte também
--------

[Visão geral do relatório eletrônico](general-electronic-reporting.md)


