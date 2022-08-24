---
title: Configurar mapeamentos do modelo ER dependente do contexto do país
description: Este artigo explica como você pode configurar os mapeamentos modelo de ER de forma que dependam do contexto de país/região da entidade legal que controla seu uso.
author: kfend
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.2
ms.custom: ''
ms.assetid: ''
ms.search.form: ERSolutionTable
ms.openlocfilehash: 5db0936682e0cc052622658ac14046013bc4fd87
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277746"
---
# <a name="configure-country-context-dependent-er-model-mappings"></a>Configurar mapeamentos de modelo de ER dependente do contexto do país

[!include[banner](../includes/banner.md)]

Você pode configurar mapeamentos de modelo de ER (Relatórios eletrônicos) para que eles implementem um modelo de dados de ER genérico mas que sejam específicos do Dynamics 365 Finance. Este artigo explica como projetar vários mapeamentos de modelo de ER para um modelo de dados de ER para controlar como eles são usados por formatos de ER correspondentes executados de empresas com contextos diferentes de país/região.

## <a name="prerequisites"></a>Pré-requisitos

Para concluir os exemplos neste artigo, você deve ter o seguinte acesso:

- Acesso ao Finance para uma das seguintes funções:
    - Desenvolvedor de relatório eletrônico
    - Consultor funcional de relatório eletrônico
    - Administrador do sistema

- Acesso à instância de RCS (Regulatory Configuration Services) que foi provisionada para o mesmo locatário do que o Finance para uma das seguintes funções:
    - Desenvolvedor de relatório eletrônico
    - Consultor funcional de relatório eletrônico
    - Administrador do sistema

Algumas etapas deste artigo exigem a execução de um formato de ER. Em alguns casos, a execução de um formato de ER é afetada pelo contexto de país/região da empresa a que você está conectado atualmente. Você poderá executar um formato de ER na instância de RCS atual se a empresa com o contexto de país/região necessário disponível no RCS. Caso contrário, você deverá fazer upload de uma versão concluída do mapeamento de modelo de ER e as configurações de formato de ER que usam o modelo de dados de ER para sua instância do Finance, e então execute o formato de ER nessa instância do Finance. Para obter informações sobre como importar as configurações que residem no RCS para uma instância do Finance, consulte [Importar configurações do RCS](rcs-download-configurations.md).

## <a name="single-model-mapping-case"></a>Caso de mapeamento de modelo único

Siga as etapas no [Apêndice 1](#appendix1) deste artigo para projetar os componentes de ER necessários. Agora você tem o mapeamento de modelo **Mapeamento (Geral)** que contém o mapeamento do modelo para a definição **Ponto de entrada 1**.

![Configurações de ER, Formatar para aprender a configuração de mapeamentos.](./media/RCS-Context-specific-mapping-Tree.PNG)

### <a name="run-the-configured-format"></a>Executar o formato configurado

1.  Na **página Configurações**, na Guia Rápida **Versões**, selecione **Executar**.
2.  Selecione **OK**.

Observe que o navegador se oferece para baixar o arquivo de texto gerado pelo formato de ER executado. Como esse formato foi configurado para usar a definição **Ponto de entrada 1** e somente um mapeamento de modelo único está disponível no momento para o modelo base com um mapeamento para essa definição, o formato de ER executado usou o mapeamento do modelo **Mapeamento (Geral)** da configuração **Mapeamento (Geral)** como uma fonte de dados. Portanto, o arquivo baixado contém o texto **Funcionalidade genérica 1**.

## <a name="multiple-shared-model-mappings-case"></a>Caso de vários mapeamentos do modelo compartilhado

Siga as etapas no [Apêndice 2](#appendix2) deste artigo para projetar os componentes de ER necessários. Agora você tem as configurações de mapeamento do modelo **Mapeamento (Geral)** e **Mapeamento (Geral)**, cada uma com o mapeamento do modelo para a definição **Ponto de entrada 1**.

![Configurações de ER, Configuração personalizada geral de mapeamento.](./media/RCS-Context-specific-mapping-TreeCustom.PNG)

### <a name="run-the-configured-format"></a>Executar o formato configurado

1.  Na página **Configurações**, na árvore de configurações, selecione **Formato para aprender mapeamentos**.
2.  Na Guia Rápida **Versões**, selecione **Executar**.
3.  Selecione **OK**.

Observe que a execução do formato de ER selecionado não obteve êxito. Uma mensagem de erro que informa mais de um mapeamento de um modelo existente para o **Modelo para aprender mapeamentos** e a definição **Ponto de entrada 1** nas configurações de mapeamentos do modelo **Mapeamento (Geral)** e **Mapeamento (Geral) personalizado**. A mensagem também recomenda que você selecione uma dessas configurações conforme a configuração padrão.

![Configurações de ER com mensagem de erro.](./media/RCS-Context-specific-mapping-FormatRunCustomFailed.PNG)

### <a name="define-a-default-mapping-configuration"></a>Definir uma configuração padrão de mapeamento

Siga estas etapas para definir a configuração de mapeamento do modelo **Mapeamento (Geral) personalizado** como a configuração padrão, para que os mapeamentos possam ser usados como fontes de dados para o formato de ER **Formato para aprender mapeamentos**.

1.  Na página **Configurações**, na árvore de configurações, selecione **Mapeamento (Geral) personalizado**.
2.  Conforme necessário, selecione **Editar** para tornar a página atual disponível para edição.
3.  Defina a opção **Padrão do mapeamento de modelo** como **Sim**.
4.  Selecione **Salvar**.

![Página Configurações de ER, Padrão para o seletor de mapeamento de modelos definido como Sim.](./media/RCS-Context-specific-mapping-MappingsCustomDefault.PNG)

### <a name="run-the-configured-format"></a>Executar o formato configurado

1.  Na página **Configurações**, na árvore de configurações, selecione **Formato para aprender mapeamentos**.
2.  Na Guia Rápida **Versões**, selecione **Executar**.
3.  Selecione **OK**.

Observe que a execução do formato de ER selecionado obteve êxito. O navegador se oferece para baixar o arquivo de texto gerado pelo formato de ER executado. Como esse formato foi configurado para usar a definição **Ponto de entrada 1** e a configuração de mapeamento do modelo **Mapeamento (Geral) personalizado** foi selecionada como a configuração padrão, o formato de ER executado usou o mapeamento do modelo **Mapeamento (Geral) cópia** da configuração **Mapeamento (Geral) personalizado** como a fonte de dados. Portanto, o arquivo baixado contém o texto **Funcionalidade genérica 1 personalizada**.

> [!NOTE]
> Se alterar a empresa a que está conectado no momento e executar esse formato de ER novamente, você obterá o mesmo conteúdo do arquivo gerado, pois a configuração de mapeamento do modelo ER padrão não contém nenhuma restrição dependente da empresa.

## <a name="multiple-mixed-model-mappings-case"></a>Caso de vários mapeamentos do modelo misturados

Siga as etapas no [Apêndice 3](#appendix3) deste artigo para projetar os componentes de ER necessários. Agora você tem as configurações **Mapeamento (Geral)**, **Mapeamento (Geral) personalizado** e **Mapeamento (FR) mapeamento de modelo** que contêm o mapeamento do modelo para a definição **Ponto de entrada 1**.

Observe que a versão 1 do mapeamento do modelo **Mapeamento (FR)** será configurada de forma que se aplique somente aos formatos de ER do modelo **Modelo para aprender mapeamentos modelagem** que são executados em empresas do Finance com o contexto do país/região francês.

![Página Configurações de ER, Configuração de mapeamento de modelos (FR).](./media/RCS-Context-specific-mapping-TreeFR.PNG)

### <a name="run-the-configured-format"></a>Executar o formato configurado

1.  Altere a empresa para **FRSI**.
2.  Na página **Configurações**, na árvore de configurações, selecione **Formato para aprender mapeamentos**.
3.  Na Guia Rápida **Versões**, selecione **Executar**.
4.  Selecione **OK**.

Observe que a execução do formato de ER selecionado obteve êxito. O navegador da Web se oferece para baixar o arquivo de texto gerado pelo formato de ER executado. Como esse formato foi configurado para usar a definição **Ponto de entrada 1** e a configuração de mapeamento do modelo **Mapeamento (Geral) personalizado** foi selecionada como a configuração padrão, o formato de ER executado usou o mapeamento do modelo **Mapeamento (Geral) cópia** da configuração **Mapeamento (Geral) personalizado** como a fonte de dados. Portanto, o arquivo baixado contém o texto **Funcionalidade genérica 1 personalizada**.

### <a name="define-the-france-specific-mapping-configuration-as-the-default-configuration"></a>Definir a configuração de mapeamento específica da França como a configuração padrão

Siga estas etapas para definir a configuração de mapeamento do modelo **Mapeamento (FR)** personalizado como a configuração padrão. Observe que, como esse mapeamento é específico da França, será considerado o mapeamento padrão entre todas as configurações de mapeamento do modelo com o código de país **FR** especificado no campo **Códigos ISO de país/região**.

1.  Na página **Configurações**, na árvore de configurações, selecione **Mapeamento (FR)**.
2.  Conforme necessário, selecione **Editar** para tornar a página atual disponível para edição.
3.  Defina a opção **Padrão do mapeamento de modelo** como **Sim**.
4.  Selecione **Salvar**.

![Página Configurações de ER, Configuração (FR) de mapeamento, Padrão para o ajuste de mapeamento de modelo definido como Sim.](./media/RCS-Context-specific-mapping-TreeFRDefault.PNG)

### <a name="run-the-configured-format"></a>Executar o formato configurado

1.  Na página **Configurações**, na árvore de configurações, selecione **Formato para aprender mapeamentos**.
2.  Na Guia Rápida **Versões**, selecione **Executar**.
3.  Selecione **OK**.

Observe que a execução do formato de ER selecionado obteve êxito. O navegador da Web se oferece para baixar o arquivo de texto gerado pelo formato de ER executado. Como esse formato foi configurado para usar a definição **Ponto de entrada 1** e a configuração de mapeamento do modelo **Mapeamento (FR) personalizado** foi selecionada como a configuração padrão, o formato de ER executado usou o mapeamento do modelo **Mapeamento (FR) cópia** da configuração **Mapeamento (FR) personalizado** como a fonte de dados. Portanto, o arquivo baixado contém o texto **Funcionalidade FR 1**.

> [!NOTE]
> Se você alterar a empresa a que está conectado no momento e executar esse formato de ER novamente, a saída dependerá do contexto de país/região da empresa selecionada.

## <a name="other-model-mapping-cases"></a>Outros casos de mapeamento do modelo

Como você viu, a seleção de um mapeamento do modelo para a execução de um formato de ER funciona da seguinte maneira:

- A definição de mapeamento do modelo que um formato de ER usa é especificada (**Ponto de entrada 1** nos exemplos deste artigo).
- Todas as configurações de mapeamentos que contêm um mapeamento com a definição especificada, e se isso satisfizer quaisquer restrições de contexto de país/região configuradas, potencialmente podem ser usadas para executar o formato de ER (**Mapeamento (Geral)**, **Mapeamento (Geral) personalizado** e **Mapeamento (FR)** nos exemplos deste artigo).
- Qualquer mapeamento do modelo padrão com restrições do contexto de país/região tem a prioridade mais alta para seleção (**Mapeamento (FR)** nos exemplos deste artigo).
- Qualquer mapeamento do modelo padrão que não tenha restrições do contexto de país/região tem a próxima prioridade mais alta para seleção (**Mapeamento (Geral)** personalizado nos exemplos deste artigo).
- Qualquer mapeamento do modelo que tenha restrições do contexto de país/região tem a prioridade mais alta para a seleção de um mapeamento do modelo que não tenha restrições do contexto de país/região.

A tabela a seguir fornece informações sobre os resultados de seleção de mapeamento do modelo para todos os casos possíveis para as configurações de mapeamento do modelo:

- A coluna 1 indica se o primeiro mapeamento do modelo que não tem restrições de contexto de país/região (por exemplo, o mapeamento **Mapeamento (Geral)** compartilhado) será apresentado e, caso seja, se a opção **Padrão para o mapeamento do modelo** está definida como **Sim** para ela.
- A coluna 2 indica se o segundo mapeamento do modelo que não tem restrições de contexto de país/região (por exemplo, o mapeamento **Mapeamento (Geral) personalizado** compartilhado) será apresentado e, caso seja, se a opção **Padrão para o mapeamento do modelo** está definida como **Sim** para ela.
- A coluna 3 indica se o primeiro mapeamento do modelo que tem restrições de contexto de país/região A (por exemplo, o mapeamento **Mapeamento (FR)** específico da França) será apresentado e, caso seja, se a opção **Padrão para o mapeamento do modelo** está definida como **Sim** para ela.
- A coluna 4 indica se o segundo mapeamento do modelo que tem restrições de contexto de país/região A será apresentado e, caso seja, se a opção **Padrão para o mapeamento do modelo** está definida como **Sim** para ela.
- A coluna 5 apresenta o resultado de uma seleção de mapeamento do modelo para a execução de um formato de ER sob o controle da empresa com o contexto de país/região A.
- A coluna 6 apresenta o resultado de uma seleção de mapeamento do modelo para a execução de um formato de ER sob o controle da empresa com o contexto de país/região B.

Na tabela, um sinal de adição (+) indica a presença de uma configuração de mapeamento do modelo na instância atual de serviço do Microsoft Azure que é usada para executar um formato de ER (Finance ou RCS).

| Caixa | Mapeamento do modelo 1 sem contexto de país/região (MM1) | Mapeamento do modelo 2 sem contexto de país/região (MM2) | Mapeamento do modelo 1 com contexto de país/região A (MM1A) | Mapeamento do modelo 2 com contexto de país/região A (MM2A) | Executar sob o controle de uma empresa com o contexto de país/região A | Executar sob o controle de uma empresa com o contexto de país/região B |
|---------|---------|---------|---------|---------|---------------------------|----------------------------|
|         |     1   |     2   |    3    |    4    |           5               |            6               |
|     1   |         |         |         |         | Erro (mapeamento ausente)   | Erro (mapeamento ausente)    |
|     2   |     +   |         |         |         | MM1                       | MM1                        |
|     3   |     +   |     +   |         |         | Erro (vários mapeamentos) | Erro (vários mapeamentos)  |
|     4   |     +   |         |    +    |         | MM1A                      | MM1                        |
|     5   |     +   |         |    +    |    +    | Erro (vários mapeamentos) | MM1                        |
|     6   |     +   | padrão |    +    |    +    | MM2                       | MM2                        |
|     7   |     +   |         | padrão |         | MM1A                      | MM1                        |
|     8   |     +   |         | padrão |    +    | MM1A                      | MM1                        |
|     9   |     +   |         | padrão | padrão | Erro (vários mapeamentos) | MM1                        |
|    10   | padrão |         |         |         | MM1                       | MM1                        |
|    11   | padrão |    +    |         |         | MM1                       | MM1                        |
|    12   | padrão |         |    +    |         | MM1                       | MM1                        |
|    13   | padrão | padrão |         |         | Erro (vários mapeamentos) | Erro (vários mapeamentos)  |
|    14   | padrão |         | padrão |         | MM1A                      | MM1                        |
|    15   | padrão |         | padrão | padrão | MM1A                      | MM2A                       |
|    16   |         |         |    +    |    +    | MM1A                      | MM2A                       |
|    17   |         |         | padrão | padrão | MM1A                      | MM2A                       |

## <a name="learn-what-mapping-was-used-in-the-execution-of-an-er-format"></a>Saiba qual mapeamento foi usado na execução de um formato de ER

### <a name="configure-er-user-parameters"></a>Configurar parâmetros de usuário de ER

1.  Na página **Configurações**, no Painel de Ação, na guia **CONFIGURAÇÕES**, selecione **Parâmetros de usuário**.
2.  Defina a opção **Executar no modo de depuração** como **Sim**.
4.  Selecione **OK**.

### <a name="run-the-configured-format"></a>Executar o formato configurado

1.  Na página **Configurações**, na árvore de configurações, selecione **Formato para aprender mapeamentos**.
2.  Na Guia Rápida **Versões**, selecione **Executar**.
3.  Selecione **OK**.

### <a name="review-the-er-debug-log"></a>Revisar o log de depuração de ER

1.  No painel de navegação, Acesse **Módulos \> Administração da organização \> Relatórios eletrônicos \> Log de depuração de configuração**.
2.  Selecione o botão **Recarregar esta página**.

![Página de logs de execução de ER.](./media/RCS-Context-specific-mapping-DebugLog.PNG)

Observe que um novo registro foi adicionado ao log de depuração de ER para o formato de ER executado. Como o campo **Nível** deste registro foi definido como **Informações**, o registro é informativo. Como o campo Formatar componente foi definido como **Configuração de mapeamento**, o registro informa sobre um mapeamento do modelo que foi usado durante a execução do formato de ER **Formato para aprender mapeamentos** (selecionado no campo **Nome da configuração**). O conteúdo do campo **Texto gerado** informa que o componente de mapeamento **Mapeamento (FR)** que reside na configuração **Mapeamento (FR)** foi usado para executar esse relatório.

## <a name="appendix-1"></a><a name="appendix1"></a> Apêndice 1

### <a name="configure-a-sample-data-model"></a>Configurar um modelo de dados de exemplo

Entre em sua instância do RCS.

Neste exemplo, você criará uma configuração para a empresa de exemplo, a Litware, Inc. Para concluir estas etapas, primeiro você deverá concluir, no RCS, as etapas do procedimento [Criar um provedor configuração e marcá-lo como ativo](tasks/er-configuration-provider-mark-it-active-2016-11.md).

#### <a name="create-an-er-data-model-configuration"></a>Criar uma configuração de modelo de dados de ER

1.  No painel padrão, selecione **Relatório eletrônico**.
2.  Selecione o bloco **Configurações de relatórios**.
3.  Na página **Configurações**, selecione **Criar configuração**.
4.  Na caixa de diálogo suspensa, no campo **Nome**, insira **Modelo para aprender mapeamentos**.
5.  Selecione **Criar configuração**.
6.  Selecione a Guia Rápida **Componentes de configuração**.

Observe que a versão de rascunho 1 dessa configuração de ER está pronta para edição. Essa versão contém o componente do modelo de dados.

#### <a name="design-a-sample-data-model"></a>Projetar um modelo de dados de exemplo

1.  Na **página Configurações**, selecione **Designer**.
2.  Selecione **Novo**.
3.  Na caixa de diálogo suspensa, no campo **Nome** , insira **Ponto de entrada 1**.
4.  Selecione **Adicionar**.
5.  Selecione **Novo**.
6.  Na caixa de diálogo suspensa, no campo **Nome**, insira **Descrição da funcionalidade**.
7.  Selecione **Adicionar**.
8.  Selecione **Novo**.
9.  Na caixa de diálogo suspensa, no grupo de campos **Novo nó**, selecione **Modelo raiz**.
10. No campo **Nome**, insira **Ponto de entrada 2**.
11. Selecione **Ponto de entrada 2**.
12. Selecione **Adicionar**.
13. Selecione **Novo**.
14. Na caixa de diálogo suspensa, no campo **Nome**, insira **Descrição da funcionalidade**.
15. Selecione **Adicionar**.

    ![Página do designer de modelo de dados de ER.](./media/RCS-Context-specific-mapping-Model.PNG)

16. Selecione **Salvar**.
17. Feche a página.

#### <a name="complete-the-modified-version-of-the-model-configuration"></a>Concluir a versão modificada da configuração do modelo

1.  Na página **Configurações**, na Guia Rápida **Versões**, selecione **Alterar status**.

    > Altere o status da configuração do modelo projetado de **Rascunho** para **Concluído**, de modo que ele possa ser usado para criar os mapeamentos e os formatos do modelo necessários.

2.  Selecione **Concluir**.
3.  Selecione **OK**.

Observe que a configuração criada será salva como a versão 1 concluída.

### <a name="configure-a-sample-model-mapping"></a>Configurar um mapeamento do modelo de exemplo

#### <a name="create-an-er-model-mapping-configuration"></a>Criar uma configuração de mapeamento do modelo de ER

1.  Na página **Configurações**, selecione **Criar configuração**.
2.  Na caixa de diálogo suspensa, no grupo de campos **Novo**, selecione **Mapeamento do modelo baseado no modelo de dados Modelo para aprender mapeamentos**.
3.  No campo **Nome**, insira **Mapeamento (Geral)**.
4.  No campo **Definição de modelo de dados**, selecione **Ponto de entrada 1**.
5.  Selecione **Criar configuração**.

Observe que a versão de rascunho 1 dessa configuração de ER está pronta para edição. Essa versão contém o componente de mapeamento do modelo.

#### <a name="design-a-sample-model-mapping"></a>Projetar um mapeamento do modelo de exemplo

1.  Na página **Configurações**, selecione **Designer**.

    Observe que o mapeamento do modelo do tipo de direção **Para modelo** foi adicionado automaticamente ao componente da definição **Ponto de entrada 1**.
    
2.  Selecione **Designer** para começar a editar o mapeamento do modelo adicionado.
3.  Na seção **Modelo de dados**, selecione **Editar**.
4.  No campo **Fórmula**, insira **"Funcionalidade genérica 1"**.
5.  Selecione **Salvar**.
6.  Feche a página **Designer de fórmulas**.

    ![Página Designer de mapeamento do modelo de ER, Definição do ponto de entrada 1.](./media/RCS-Context-specific-mapping-Mapping1.PNG)

7.  Selecione **Salvar**.
8.  Feche a página **Designer de mapeamento de modelo**.
9.  Selecione **Novo**.
10. No campo **Definição**, selecione **Ponto de entrada 2**.
11. No campo **Nome**, insira **Mapeamento (Geral) 2**.
12. Selecione **Designer**.
13. Na seção **Modelo de dados**, selecione **Editar**.
14. No campo **Fórmula**, insira **"Funcionalidade genérica 2"**.
15. Selecione **Salvar**.
16. Feche a página **Designer de fórmulas**.

    ![Página Designer de mapeamento do modelo de ER, Definição do ponto de entrada 2.](./media/RCS-Context-specific-mapping-Mapping2.PNG)

17. Selecione **Salvar**.
18. Feche a página **Designer de mapeamento de modelo**.

    ![Página Mapeamentos de modelo com definições do ponto de entrada.](./media/RCS-Context-specific-mapping-Mappings.PNG)

19. Feche a página **Mapeamentos de modelo**.

#### <a name="complete-the-modified-version-of-the-model-mapping-configuration"></a>Concluir a versão modificada da configuração de mapeamento do modelo

1.  Na **página Configurações**, na Guia Rápida **Versões**, selecione **Alterar status**.

    > Altere o status da configuração de mapeamento do modelo projetado de **Rascunho** para **Concluído**, de modo que ele possa ser usado por formatos de ER.

2.  Selecione **Concluir**.
3.  Selecione **OK**.

Observe que a configuração criada será salva como a versão 1 concluída.

### <a name="configure-a-sample-format"></a>Configurar um formato de exemplo

#### <a name="create-an-er-format-configuration"></a>Criar uma configuração de formato de ER

1.  Na página **Configurações**, na árvore de configurações, selecione **Modelo para aprender mapeamentos**.
2.  Selecione **Criar configuração**.
3.  Na caixa de diálogo suspensa, no grupo do campo **Novo**, selecione **Formato baseado no modelo de dados Modelo para aprender mapeamentos**.
4.  No campo **Nome**, insira **Formato para aprender mapeamentos**.
5.  No campo **Definição de modelo de dados**, selecione **Ponto de entrada 1**.
6.  Selecione **Criar configuração**.

Observe que a versão de rascunho 1 dessa configuração de ER está pronta para edição. Essa versão contém o componente do formato.

#### <a name="design-a-sample-format"></a>Projetar um formato de exemplo

1.  Na página **Configurações**, selecione **Designer**.
2.  Selecione **Adicionar raiz**.
3.  No grupo **Texto**, selecione o item **Cadeia de caracteres**.
4.  Selecione **OK**.

#### <a name="bind-format-elements-to-a-data-source"></a>Associar elementos de formato a uma fonte de dados

1.  Na página **Designer de formato** , na guia **Mapeamento** , expanda a fonte de dados do modelo.
2.  Selecione o campo **Descrição de funcionalidade**.
3.  Selecione **Associar**.

    ![Página de designer de formato de ER.](./media/RCS-Context-specific-mapping-Format.PNG)

4.  Selecione **Salvar**.
5.  Feche a página.

## <a name="appendix-2"></a><a name="appendix2"></a> Apêndice 2

### <a name="configure-a-sample-model-mapping-for-general-customization"></a>Configurar um mapeamento do modelo de exemplo para personalização geral

Talvez você queira personalizar um mapeamento do modelo que um provedor de configuração (parceiro) forneceu a você e então usar a versão personalizada como uma fonte de dados para seus formatos de ER. Nesse caso, você deve criar uma configuração de mapeamento do modelo de ER personalizada para fazer as alterações necessárias nos mapeamentos do modelo existente. Os procedimentos deste apêndice usam o mapeamento do modelo **Mapeamento (Geral)** como um exemplo.

#### <a name="create-an-er-model-mapping-configuration"></a>Criar uma configuração de mapeamento do modelo de ER

1.  Na página **Configurações**, na árvore de configurações, selecione **Mapeamento (Geral)**.
2.  Selecione **Criar configuração**.
3.  Na caixa de diálogo suspensa, no grupo de campos **Novo**, selecione **Deriva do Nome: Mapeamento (Geral), Litware, Inc.**.
4.  No campo **Nome**, insira **Mapeamento (Geral) personalizado**.
5.  Selecione **Criar configuração**.

Observe que a versão de rascunho 1 dessa configuração de ER está pronta para edição.

#### <a name="design-a-sample-model-mapping"></a>Projetar um mapeamento do modelo de exemplo

1.  Na página **Configurações**, selecione **Designer**.

    > Observe que os mapeamentos do modelo da configuração básica foram copiados automaticamente para essa configuração.

2.  Selecione o mapeamento **Mapeamento (Geral) Cópia**.
3.  Selecione **Designer**.
4.  Na seção **Modelo de dados**, selecione **Editar**.
5.  No campo **Fórmula**, insira **"Funcionalidade genérica 1 personalizada"**.
6.  Selecione **Salvar**.
7.  Feche a página.

    ![Página Designer de mapeamento do modelo de ER, Fórmula personalizada de funcionalidade genérica 1.](./media/RCS-Context-specific-mapping-Mapping1Custom.PNG)

8.  Selecione **Salvar**.
9.  Feche a página.
10. Selecione o mapeamento **Mapeamento (Geral) 2 Cópia**.
11. Selecione **Designer**.
12. Na seção **Modelo de dados**, selecione **Editar**.
13. No campo **Fórmula**, insira **"Funcionalidade genérica 2 personalizada"**.
14. Selecione **Salvar**.
15. Feche a página.

    ![Página Designer de mapeamento do modelo de ER, Fórmula personalizada de funcionalidade genérica 2.](./media/RCS-Context-specific-mapping-Mapping2Custom.PNG)

16. Selecione **Salvar**.
17. Feche a página.

    ![Página Modelo de ER para a mapeamento de datasource para Mapeamento (Geral) copiar mapeamento.](./media/RCS-Context-specific-mapping-MappingsCustom.PNG)

18. Feche a página.

#### <a name="complete-the-modified-version-of-the-model-mapping-configuration"></a>Concluir a versão modificada da configuração de mapeamento do modelo

1.  Na página **Configurações**, na Guia Rápida **Versões**, selecione **Alterar status**.

    > Altere o status da configuração de mapeamento do modelo projetado de **Rascunho** para **Concluído**, de modo que ele possa ser usado por formatos de ER.

2.  Selecione **Concluir**.
3.  Selecione **OK**.

Observe que a configuração criada será salva como a versão 1 concluída.

## <a name="appendix-3"></a><a name="appendix3"></a> Apêndice 3

### <a name="configure-a-sample-model-mapping-for-countryregion-specific-customization"></a>Configurar um mapeamento do modelo de exemplo para personalização específica do país/região

Para alguns formatos de ER, pode haver requisitos específicos do país/requisitos para a preparação de dados. Nesse caso, você pode gerenciar uma configuração separada de mapeamento do modelo de ER e isolar a implementação desses requisitos de país/região específicos da implementação geral. Os procedimentos deste apêndice usam o formato de ER **Formato para aprender mapeamentos** e os requisitos específicos do francês como um exemplo.

#### <a name="create-an-er-model-mapping-configuration"></a>Criar uma configuração de mapeamento do modelo de ER

Primeiro, crie uma nova configuração de mapeamento do modelo de ER para implementar os requisitos específicos do país/região. Use a configuração de mapeamento do modelo de ER personalizada como base.

1.  Na página **Configurações**, na árvore de configurações, selecione **Mapeamento (Geral) personalizado**.
2.  Selecione **Criar configuração**.
3.  Na caixa de diálogo suspensa, no grupo de campos **Novo**, selecione **Deriva do Nome: Mapeamento (Geral) personalizado, Litware, Inc.**.
4.  No campo **Nome**, insira **Mapeamento (FR)**.
5.  Selecione **Criar configuração**.

Observe que a versão de rascunho 1 dessa configuração de ER está pronta para edição.

#### <a name="design-a-sample-model-mapping"></a>Projetar um mapeamento do modelo de exemplo

1.  Na página **Configurações**, selecione **Designer**.

    > Observe que os mapeamentos do modelo da configuração básica foram copiados automaticamente para essa configuração.

2.  Selecione o mapeamento **Mapeamento (Geral) Cópia Cópia**.
3.  Renomeie-o como **Mapeamento (FR)**.
4.  Selecione **Designer**.
5.  Na seção **Modelo de dados**, selecione **Editar**.
6.  No campo **Fórmula**, insira **"Funcionalidade FR 1"**.
7.  Selecione **Salvar**.
8.  Feche a página.

    ![Página Designer de mapeamento do modelo de ER, Fórmula de funcionalidade 1 FR.](./media/RCS-Context-specific-mapping-Mapping1FR.PNG)

9.  Selecione **Salvar**.
10. Feche a página.
11. Selecione o mapeamento **Mapeamento (Geral) 2 Cópia Cópia**.
12. Renomeie-o como **Mapeamento (FR) 2**.
13. Selecione **Designer**.
14. Na seção **Modelo de dados**, selecione **Editar**.
15. No campo **Fórmula**, insira **"Funcionalidade FR 2"**.
16. Selecione **Salvar**.
17. Feche a página.

    ![Página Designer de mapeamento do modelo de ER, Fórmula de funcionalidade 2 FR.](./media/RCS-Context-specific-mapping-Mapping2FR.PNG)

18. Selecione **Salvar**.
19. Feche a página.

    ![Página Mapeamento de modelo de ER para fonte de dados.](./media/RCS-Context-specific-mapping-MappingsFR.PNG)

20. Feche a página.

#### <a name="specify-countryregion-context-restrictions-for-use"></a>Especificar restrições de contexto do país/região para uso

1.  Na página **Configurações**, na Guia Rápida **Códigos ISO de país/região**, selecione **Novo**.
2.  No campo **ISO**, selecione **FR**.
3.  Selecione **Salvar**.

Observe que é necessário conectar-se a uma empresa específica no Finance para executar um formato de ER. Portanto, essa empresa pode ser considerada um participante que controla a execução do formato de ER e a seleção do mapeamento do modelo de ER correto do modelo de dados de ER base. Ao adicionar o código de país **FR**, você especifica que esse mapeamento do modelo só estará disponível para seleção por um formato de ER do modelo de dados base quando o formato for executado sob o controle de uma empresa com o contexto de país/região francês.

Você pode adicionar vários códigos de país/região para uma única versão da configuração de um mapeamento do modelo de ER. Assim, os mapeamentos do modelo que residem nessa configuração de mapeamento do modelo podem ser usados para um formato de ER que é executado sob o controle de empresas com um contexto de país/região diferente.

Observe que a lista de códigos de país/região será especificada para cada versão de uma configuração de mapeamento do modelo de ER e podem variar de versão para versão.

#### <a name="complete-the-modified-version-of-the-model-mapping-configuration"></a>Concluir a versão modificada da configuração de mapeamento do modelo

1.  Na página **Configurações**, na Guia Rápida **Versões**, selecione **Alterar status**.

    > Altere o status da configuração de mapeamento do modelo projetado de **Rascunho** para **Concluído**, de modo que ele possa ser usado por formatos de ER.

2.  Selecione **Concluir**.
3.  Selecione **OK**.

Observe que a configuração criada será salva como a versão 1 concluída.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de Relatório eletrônico (ER)](general-electronic-reporting.md)

[Gerenciar o mapeamento do modelo de ER em configurações ER separadas](./tasks/er-manage-model-mapping-configurations-july-2017.md)

[Aplicar contexto de país/região](../lcs-solutions/apply-country-context.md)

## <a name="frequently-asked-questions"></a>Perguntas frequentes

#### <a name="i-configured-two-shared-er-model-mapping-configurations-in-rcs-and-marked-one-of-them-as-the-default-model-mapping-configuration-i-successfully-ran-an-er-format-that-was-created-for-the-same-base-er-data-model-configuration-to-test-model-mappings-i-then-imported-the-whole-er-solution-er-data-model-two-er-model-mapping-configurations-and-er-format-configuration-into-finance-why-do-i-receive-an-error-message-when-i-try-to-run-the-same-er-format-in-finance"></a>Eu defini duas configurações de mapeamento do modelo de ER compartilhadas no RCS e marquei uma delas como a configuração do mapeamento do modelo padrão. Eu executei com êxito um formato de ER que foi criado pela mesma configuração de modelo de dados de ER base para testar mapeamentos do modelo. Então importei a solução de ER inteira (modelo de dados de ER, duas configurações de mapeamento do modelo de ER e configuração do formato de ER) para Finance. Por que eu recebo um erro quando tento executar o mesmo formato de ER no Finance?
A configuração de mapeamento do modelo padrão é específica do ambiente. Ela deve ser definida no RCS, mas não é exportada para o Finance. Para executar com êxito esse formato de ER, você também deverá marcar uma das configurações de mapeamento do modelo de ER como a configuração de mapeamento do modelo padrão no Finance.

#### <a name="i-configured-one-model-mapping-as-a-shared-model-mapping-and-completed-the-draft-version-of-it-i-then-added-a-new-model-mapping-configuration-for-same-data-model-and-configured-it-as-french-specific-why-is-the-shared-model-mapping-selected-when-i-run-an-er-format-even-though-this-er-format-uses-the-correct-root-definition-and-execution-is-done-under-the-control-of-the-company-that-has-french-countryregion-context"></a>Eu configurei um mapeamento do modelo como um mapeamento do modelo compartilhado e concluí a versão de rascunho dele. Adicionei uma nova configuração de mapeamento do modelo para o mesmo modelo de dados e a configurei como específica do francês. Por que o mapeamento do modelo compartilhado selecionado quando executo um formato de ER mesmo que esse formato de ER use a definição de raiz correta e a execução é feita sob o controle da empresa com o contexto de país/região francês?
Verifique se a configuração de mapeamento do modelo compartilhado não está marcada como a configuração de mapeamento do modelo padrão. Caso contrário, ela terá uma prioridade mais alta durante a seleção de mapeamento. Verifique também se a configuração de mapeamento do modelo específico do francês é considerada quando um mapeamento é selecionado durante a execução do formato de ER. Uma configuração de mapeamento do modelo de ER só estará disponível para seleção se pelo menos uma das seguintes condições for atendida:
- Pelo menos uma versão da configuração de mapeamento do modelo de ER tem o status **Concluído** ou **Compartilhado**. Nesse caso, a versão com o número de versão mais alto será usada para a execução do formato de ER.
- A opção **Executar rascunho** para o mapeamento do modelo de ER está ativada. Nesse caso, a versão com o status **Rascunho** será usada para a execução do formato de ER.
> A opção **Executar rascunho** se tornará disponível na página **Configurações** para cada configuração de mapeamento do modelo de ER quando o parâmetro de usuário de ER **Executar configuração** estiver ativado.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
