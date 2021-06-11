---
title: Inserir habilidades
description: Trabalhadores e gerentes podem inserir habilidades no Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: b24d37292a2e9749fb2fde06b9f03fcd13db0bbe
ms.sourcegitcommit: 48528233e0f02dbd47e96e030254ef65f2bb899e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "6076578"
---
# <a name="enter-skills"></a>Inserir habilidades

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Você pode inserir habilidades alvo ou habilidades reais para trabalhadores, candidatos ou contatos no Dynamics 365 Human Resources. Uma habilidade alvo é uma habilidade que uma pessoa planeja obter. Uma habilidade real é uma habilidade que uma pessoa tem atualmente.

## <a name="create-a-workflow-to-auto-approve-skills"></a>Criar um fluxo de trabalho para aprovar habilidades automaticamente

Para inserir habilidades sem exigir aprovação, você deve criar um fluxo de trabalho para aprovar habilidades automaticamente.

> [!NOTE]
> As habilidades inseridas pelos trabalhadores sempre exigem aprovação do gerente. Esse fluxo de trabalho aprova automaticamente as habilidades inseridas por gerentes em nome de seus trabalhadores.

1. No espaço de trabalho **Gerenciamento de pessoal**, selecione **Links**.

2. Em **Configuração**, selecione **Fluxos de trabalho de recursos humanos**.

3. Selecione **Novo**.

4. No painel **Criar fluxo de trabalho**, selecione **Habilidades do trabalhador**.

   [![Selecionar fluxo de trabalho de habilidades do Trabalhador](media/hr-develop-skills-new-workflow.png)](media/hr-develop-skills-new-workflow.png)

5. Na caixa de diálogo **Abrir este arquivo?**, selecione **Abrir**. Quando solicitado, insira as credenciais.

6. No editor de fluxo de trabalho, selecione o elemento do fluxo de trabalho **Aprovar habilidades** e arraste-o para a tela.

   [![Selecionar elemento de fluxo de trabalho Aprovar habilidades](media/hr-develop-skills-element.png)](media/hr-develop-skills-element.png)

7. Conecte o elemento **Iniciar** ao elemento **Aprovar habilidades 1** e, em seguida, conecte o elemento **Aprovar habilidades 1** ao elemento **Finalizar**. Talvez seja necessário rolar para baixo para ver o elemento **Finalizar**. Você pode arrastá-lo para mais perto dos outros elementos.

   [![Conectar elementos de fluxo de trabalho](media/hr-develop-skills-connect-elements.png)](media/hr-develop-skills-connect-elements.png)

8. Clique duas vezes no elemento de fluxo de trabalho **Aprovar habilidades 1** e clique com o botão direito do mouse no elemento **Etapa 1**. Clique com o botão direito do mouse no elemento **Etapa 1** e selecione **Propriedades**.

9. Na janela **Propriedades**, selecione **Condição** na barra de navegação à esquerda.

10. Selecione **Executar esta etapa somente quando a seguinte condição for atendida**.

11. Selecione **Adicionar condição**. Depois de **Onde**, selecione **Habilidades de autoatendimento para funcionários** e depois selecione **Habilidades de autoatendimento para funcionários - Pessoa**. Depois de **é**, selecione **campo** e selecione **Relacionamento de Usuário para pessoa - Pessoa**.

    [![Especificar condição](media/hr-develop-skills-condition.png)](media/hr-develop-skills-condition.png)

12. Selecione **Atribuição** na barra de navegação à esquerda.

13. Na guia **Tipo de atribuição**, selecione **Hierarquia**.

14. Na guia **Seleção de hierarquia**, no campo **Tipo de hierarquia:**, selecione **Hierarquia gerencial**.

    [![Especificar hierarquia administrativa](media/hr-develop-skills-hierarchy.png)](media/hr-develop-skills-hierarchy.png)

15. Selecione **Fechar**, escolha **Fluxo de trabalho** na trilha de navegação da tela e selecione **Salvar e fechar**.

Para obter mais informações sobre como criar fluxos de trabalho, consulte [Visão geral do sistema de fluxo de trabalho](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/overview-workflow-system?toc=/dynamics365/human-resources/toc.json).

## <a name="enter-skills-for-a-worker"></a>Inserir habilidades para um trabalhador

1. Selecione um trabalhador.

2. Na barra de ação da página **Trabalhador**, selecione **Pessoa** e depois **Habilidades**.

3. Na página **Habilidades**, preencha os seguintes campos para cada habilidade:

   - **Habilidade**: selecione uma habilidade.
   - **Tipo de nível**: selecione **Real** para uma habilidade que o trabalhador já tenha ou selecione **Alvo** para uma habilidade em que o trabalhador está trabalhando.
   - **Nível**: selecione um nível para a habilidade do trabalhador.
   - **Data do nível**: selecione uma data na ferramenta do calendário.
   - **Examinador**: se apropriado, selecione um examinador na lista. Você pode filtrar sua pesquisa.
   - **Anos de experiência**: insira anos de experiência.
   - **Verificado**: se a habilidade for verificada, marque a caixa.
   - **Verificado por**: insira o nome do verificador.

4. Quando tiver concluído a inserção de habilidades, selecione **Salvar**.

## <a name="see-also"></a>Consulte também

[Configurar habilidades](hr-develop-skills.md)<br>
[Mapear habilidades](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]