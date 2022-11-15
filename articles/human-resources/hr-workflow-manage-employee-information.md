---
title: Usar fluxos de trabalho para gerenciar informações de funcionários
description: Este artigo explica como você pode usar fluxos de trabalho para gerenciar informações de funcionários.
author: twheeloc
ms.date: 11/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: dbbbb0ee807cb65fa4f4f9a29cc4a2b6b045b08c
ms.sourcegitcommit: 2b654e60e2553a5835ab5790db4ccfa58828fae7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2022
ms.locfileid: "9750725"
---
# <a name="use-workflows-to-manage-employee-information"></a>Usar fluxos de trabalho para gerenciar informações de funcionários

[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo explica como você pode usar o recurso de fluxo de trabalho para recursos humanos para gerenciar informações de funcionários. Por exemplo, você pode associar um fluxo de trabalho a uma posição e configurar um fluxo de trabalho de aprovação que é iniciado quando os funcionários alteram seu registro.

A capacidade de fluxo de trabalho para Recursos Humanos fornece vários fluxos de trabalho para gerenciar atividades de recursos humanos. Além disso, várias opções estão disponíveis para que você possa modificar fluxos de trabalho específicos e associá-los a uma hierarquia de relatórios. Os fluxos de trabalho estão disponíveis para ajudar a gerenciar alterações a vários tipos de informações de funcionários. Você pode associar um fluxo de trabalho a uma posição. Em seguida, se os funcionários alterarem o registro do funcionário, será iniciado um fluxo de trabalho que requer aprovação antes que as novas informações sejam salvas. Os fluxos de trabalho são predefinidos para os seguintes tipos de informações para ajudá-lo a gerenciar com eficiência as alterações e manter os dados dos funcionários precisos:

-   Números de identificação
-   Cursos
-   Formação
-   Imagem
-   Itens emprestados
-   Experiência profissional
-   Experiência em projetos
-   Habilidades
-   Posições de confiança
-   Ações de recursos humanos
-   Registro do curso

Quando os funcionários são contratados, transferidos ou encerrados, o fluxo de trabalho pode incluir um processo de revisão. Desta forma, um documento poderá ser revisado ou os termos de uma ação poderão ser definidos como parte do fluxo de trabalho. Quando o processo de revisão é concluído, o documento ou ação é concluído e o fluxo de trabalho passa para uma etapa de aprovação final.

## <a name="associate-a-workflow-with-a-position-hierarchy"></a>Associar um fluxo de trabalho a uma hierarquia de posições

Você pode associar um fluxo de trabalho a qualquer hierarquia da posição que você configurar. Dois tipos de hierarquia são usados para o roteamento de fluxo de trabalho: **Gerencial** e **Configurável**.

- Uma hierarquia **Administrativa** representa a estrutura hierárquica da empresa ou da organização. Para obter mais informações sobre esse tipo de hierarquia, consulte [Cargo Subordinado de](hr-personnel-positions.md#reports-to-position).
- Uma hierarquia **Configurável** representa uma hierarquia de matriz ou personalizada. Para obter mais informações sobre esse tipo de hierarquia, consulte [Relacionamentos](hr-personnel-positions.md#relationships).

### <a name="managerial-hierarchy-example"></a>Exemplo de hierarquia administrativa

Você pode configurar um fluxo de trabalho para que, quando um funcionário enviar uma solicitação de compra para um novo computador, a solicitação seja roteada para o gerente do funcionário e o gerente de nível hierárquico. Ao configurar a etapa do fluxo de trabalho, defina o campo **Tipo de atribuição** como **Hierarquia**. A guia **Tipo de hierarquia** será disponibilizada. Para este exemplo, selecione a hierarquia **Administrativa**.

### <a name="configurable-hierarchy-example"></a>Exemplo de hierarquia configurável

Se uma posição estiver associada a uma hierarquia de relatórios de matriz, você pode configurar um fluxo de trabalho que encaminha despesas para um projeto específico, para a liderança do projeto, em vez do gerente do funcionário. Nesse caso, defina o campo **Tipo de atribuição** como **Hierarquia**. Em seguida, na guia **Tipo de hierarquia**, selecione a hierarquia **Configurável**. Depois que o fluxo de trabalho for configurado, selecione a hierarquia **Associar** na página **Configuração do fluxo de trabalho** para selecionar a hierarquia que deve ser usada para o roteiro do fluxo de trabalho.

> [!IMPORTANT]
> Quando um documento, uma transação ou um registro mestre for enviado para a aprovação do fluxo de trabalho, a posição principal do emissor será usada para determinar para quem o documento deve ser encaminhado na próxima vez.

### <a name="hierarchy-setting-in-workflow-parameters"></a>Configuração de hierarquia em parâmetros de Fluxo de trabalho

1. Na página **Parâmetros de fluxo de trabalho** vá para **Roteiro da hierarquia**.
2. Por padrão, a opção **Usar hierarquia de cargos** está definida como **Não**. Nesse caso, o fluxo de trabalho usará a posição principal do trabalhador quando navegar na hierarquia. Defina a opção como **Sim** para fazer com que o fluxo de trabalho use o pai da posição ao navegar na hierarquia.

### <a name="additional-example"></a>Exemplo adicional 

A funcionária Grace Sturman tem duas posições: consultora e instrutora. A posição principal da Grace é instrutora. Quando ela não está treinando novos funcionários, ela está disponível para o trabalho de consultoria. Por meio da sua posição principal, Grace se reporta a Clair, o Diretor de Recursos Humanos. Claire se reporta a Charlie. Para a posição do consultor, Grace tem vários relacionamentos indiretos, dependendo do projeto.

A empresa de Grace cria regras de roteamento de fluxo de trabalho com base em uma hierarquia **Configurável** (hierarquias baseadas em matriz/projeto). Esta hierarquia usa a posição de consultor de Grace. Se a opção **Usar hierarquia da posição** estiver definida como **Não**, quando um documento for encaminhado para Grace para sua aprovação, o fluxo de trabalho verificará a posição principal (instrutor) para determinar para onde o documento deve ser encaminhado em seguida. Nesse caso, ele será encaminhado primeiro para Claire, e depois para Charlie. Se a opção estiver definida como **Sim** e o fluxo de trabalho usar uma hierarquia **Configurável**, o fluxo de trabalho verificará a posição de consultor de Grace e a relação de subordinação para determinar para onde o documento deve ser encaminhado, posteriormente.

### <a name="configure-a-human-resources-workflow"></a>Configurar um fluxo de trabalho de recursos humanos
Para configurar um fluxo de trabalho básico que é iniciado quando os funcionários solicitam alterações à sua identificação pessoal, siga estas etapas.

1.  Na página **Fluxos de trabalho de recursos humanos**, selecione **Novo**.
2.  Na lista de fluxos de trabalho disponíveis, selecione **Números de identificação**.
3.  Selecione **Executar** para abrir o Designer de fluxo de trabalho e insira o nome de usuário e senha.
4.  Mova o elemento **Aprovar número de identificação** da lista de elementos de fluxo de trabalho para a tela do designer.
5.  Conecte o elemento de aprovação com **Início** e **Término**.
6.  Toque duas vezes (ou clique duas vezes) em **Aprovar elemento**, selecione e segure (ou clique com o botão direito do mouse) e, em seguida, selecione **Propriedades**.
7.  Siga essas etapas para adicionar instruções de item de trabalho:

    1.  Selecione **Atribuição** e, em seguida, selecione **Hierarquia** no tipo de atribuição.
    2.  Na seleção de **Hierarquia**, selecione **Hierarquia configurável**.
    3.  Adicione uma condição de parada, e feche a página.

8.  Conclua as instruções adicionais.
9.  Selecione **Salvar e fechar**. Ative o novo fluxo de trabalho quando a caixa de diálogo abrir e selecione **Ativar**.
10. Acesse **Recursos humanos** &gt; **Posições** &gt; **Tipos de hierarquia de posição**.
11. Selecione **Matriz**.
12. Adicione o fluxo de trabalho **Número de identificação do trabalhador** à lista.

## <a name="additional-resources"></a>Recursos adicionais

[Exibir e gerenciar alterações de endereço](hr-personnel-view-address-changes.md) 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
