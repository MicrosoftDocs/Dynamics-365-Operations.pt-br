---
title: Exportar dados do Attract e do Onboard
description: Exporte dados do Dynamics 365 Talent - Attract e Onboard.
author: andreabichsel
manager: AnnBe
ms.date: 01/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: Talent October 2019 update
ms.openlocfilehash: eb97a16c15476c2f34ec581a32a677fa6fee8739
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4460274"
---
# <a name="export-data-from-attract-and-onboard"></a>Exportar dados do Attract e do Onboard

[!include [banner](includes/banner.md)]

Como anunciado em [Desativar os aplicativos Dynamics 365 Talent: Attract e Dynamics 365 Talent: Onboard](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps), vamos desativar o Dynamics 365 Talent: Attract e o Dynamics 365 Talent: Onboard em 1º de fevereiro de 2022. Para ajudar na migração para outro produto, agora os dois aplicativos têm recursos de exportação de dados.

## <a name="export-data-from-attract"></a>Exportar dados do Attract

Você pode exportar dados sem restringir o acesso ao ambiente. Convém fazer isso para fins de teste ou para compreender nossa estrutura de dados. Quando estiver pronto para migrar, restrinja o acesso ao ambiente do Attract seguindo as instruções depois deste procedimento. Certifique-se de exportar os dados novamente. 

1. Acesse [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).

2. Em **Exportação de dados**, selecione **Solicitar exportação de dados**.

   ![[Solicitar exportação de dados do Attract](./media/attract-onboard-export-data-attract-request.png)](./media/attract-onboard-export-data-attract-request.png)

3. Quando a caixa de mensagem **Sua solicitação está sendo processada** for exibida, selecione **OK**. A exportação de dados pode levar até 20 minutos, dependendo do tamanho.

4. Quando a exportação for concluída, selecione o botão **Baixar** ao lado dela. 

   >[!NOTE]
   >Todas as exportações de dados ficam disponíveis por sete dias, quando então o link **Baixar** expira.</br>
   
O download contém um arquivo. zip com os dados do Attract, incluindo as seguintes pastas:

| Nome da pasta | Descrição |
| --- | --- |
| Configurações do administrador | Configurações do centro de administração do Attract. |
| Candidatos | Todos os candidatos adicionados a trabalhos ou grupos de talentos. |
| Modelos de email | Todos os modelos de email configurados para o ambiente. |
| Modelos de pacote de oferta de trabalho | Todos os modelos de pacote de oferta de trabalho que foram criados e as configurações associadas. |
| Conjuntos de regras de oferta de trabalho |  Todos os arquivos de conjunto de regras carregados para gerenciamento de ofertas. |
| Modelos de oferta de trabalho | Todos os modelos de documento de oferta de trabalho criados para o ambiente. |
| Oportunidades de emprego | Todos os trabalhos criados. Os trabalhos excluídos não são exportados. As subpastas contêm solicitações de emprego de candidatos, com subpastas para os anexos dessas solicitações e pacotes de oferta, quando aplicável. |
| Modelos de oportunidade de emprego | Os modelos de processo de trabalho configurados no ambiente. |
| Grupos de talentos | Todos os grupos de talentos criados, as respectivas listas de colaboradores e as listas de candidatos para os grupos de talentos. |
| Trabalhadores | Lista de todos os trabalhadores presentes no ambiente, além de suas funções. |
| (pasta raiz) | Um arquivo de esquema JSON que descreve os campos da estrutura de dados. |

### <a name="restrict-access-to-attract"></a>Restringir acesso ao Attract

Quando estiver pronto para migrar, restrinja o acesso de não administradores ao ambiente do Attract e exporte os dados.

>[!IMPORTANT]
>A restrição do acesso ao ambiente do Attract é permanente e não pode ser desfeita. Se você quiser que os usuários que não são administradores continuem acessando o ambiente, ignore esta etapa.

1. Acesse [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).

2. Para impedir o acesso de usuários que não são administradores ao ambiente do Attract, em **Restringir acesso a este aplicativo**, selecione **Restringir acesso agora**. A restrição do acesso também cancelará o lançamento de todos os trabalhos ativos já lançados.

   ![[Restringir acesso de não administradores ao Attract](./media/attract-onboard-export-data-attract-restrict-access.png)](./media/attract-onboard-export-data-attract-restrict-access.png)

3. Quando você vir o aviso **Esta é uma alteração permanente**, selecione **Restringir acesso** para restringir permanentemente os usuários não administradores do ambiente. Se você não estiver pronto para realizar esta etapa, selecione **Cancelar**.

   ![[Aviso que a restrição de acesso é uma alteração permanente](./media/attract-onboard-export-data-attract-warning.png)](./media/attract-onboard-export-data-attract-warning.png)

   >[!NOTE]
   >Os administradores podem continuar acessando as páginas de exportação de dados e de relatório de pessoas depois que você restringir o acesso ao ambiente do Attract.

## <a name="export-data-from-onboard"></a>Exportar dados do Onboard

Quando estiver pronto, você poderá baixar modelos, guias e dados de candidatos do Onboard.

1. Acesse [https://aka.ms/OnboardDataExport](https://aka.ms/OnboardDataExport).

2. Em **Exportação de dados**, selecione **Solicitar exportação de dados**. 

   ![[Solicitar exportação de dados do Onboard](./media/attract-onboard-export-data-onboard-request.png)](./media/attract-onboard-export-data-onboard-request.png)

3. Quando a caixa de mensagem **Sua solicitação está sendo processada** for exibida, selecione **OK**. A exportação de dados pode levar até 20 minutos, dependendo do tamanho.

4. Quando a exportação for concluída, selecione o botão **Baixar** ao lado dela. 

   ![[Baixar exportação de dados do Onboard](./media/attract-onboard-export-data-onboard-download.png)](./media/attract-onboard-export-data-onboard-download.png)

   >[!NOTE]
   >A exportação de dados fica disponível por sete dias. Após sete dias, o link **Baixar** expira e você deverá solicitar uma nova exportação se precisar baixar os dados novamente. Quando você iniciar uma nova exportação de dados, todos os downloads existentes expirarão depois que a nova exportação for concluída com êxito.

O download é um arquivo. zip que contém o seguinte:

- Uma pasta **Modelos**, que contém os modelos do Onboard no formato de documento do Word.

- Uma pasta **Guias**, que contém os guias do Onboard no formato de documento do Word.

## <a name="see-also"></a>Consulte também

[Desativar os aplicativos Dynamics 365 Talent: Attract e Dynamics 365 Talent: Onboard](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps)