---
title: Prepare metadados específicos do aplicativo para RCS e ER
description: Este tópico explica como preparar metadados específicos do aplicativo para o RCS (Regulatory Configuration Service) e ER (relatório eletrônico).
author: NickSelin
manager: AnnBe
ms.date: 04/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 89d36c305bc9210f7906cd4288e33e5028baecdb
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771251"
---
# <a name="prepare-application-specific-metadata-for-rcs-and-er"></a>Prepare metadados específicos do aplicativo para RCS e ER

[!include[banner](../includes/banner.md)]

Este tópico mostra exemplos das seguintes tarefas:

- [Preparar metadados do aplicativo que podem ser usados no RCS](#prepare-application-metadata-that-can-be-used-in-rcs)
- [Acessar metadados do aplicativo usando uma configuração do ER](#access-application-metadata-by-using-an-er-configuration)
- [Acessar metadados do aplicativo usando aplicativos conectados](#access-application-metadata-by-using-connected-applications)

## <a name="prepare-application-metadata-that-can-be-used-in-rcs"></a>Preparar metadados do aplicativo que podem ser usados no RCS

O procedimento a seguir mostra como um usuário com a função de **Administrador do Sistema** ou **Desenvolvedor de Relatório Eletrônico** pode criar uma configuração de relatório eletrônico (ER) que contém metadados do aplicativo e que é usada para criar configurações de mapeamentos do modelo ER no Regulatory Configuration Service (RCS). A configuração de mapeamento do modelo ER de exemplo que é criada neste exemplo será usada para acessar transações de comércio exterior.

Neste exemplo, você deseja utilizar o RCS para criar uma solução de ER para o aplicativo que será usado para gerar documentos eletrônicos com informações do domínio comercial de comércio exterior. Para especificar o mapeamento entre o modelo de dados de ER e as fontes de dados necessários, você precisa ter acesso a metadados do aplicativo no RCS. Portanto, como parte do processo de criação da solução de ER, você precisa definir uma nova configuração de metadados de ER contendo todos os metadados atualmente necessários para gerar relatórios de ER para o domínio comercial selecionado.

> [!NOTE]
> Neste exemplo, você criará uma configuração para a empresa de exemplo, Litware, Inc. Estas etapas podem ser executadas em qualquer empresa.

1. Ir para **Administração da organização \> Espaços de trabalho \> Relatório eletrônico**.
2. Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como **Ativo**. Se você não visualizar este provedor de configuração, conclua o procedimento [Criar provedores de configuração e marcá-los como ativos](tasks/er-configuration-provider-mark-it-active-2016-11.md). 
3. Selecione **Configurações de metadados**.
4. Selecione **Criar configuração**.
5. Na caixa de diálogo suspensa, no campo **Nome** , digite um nome. Para este exemplo, insira **Metadados de comércio exterior**.
6. Selecione **Criar configuração**.
7. Selecione **Designer**.
8. Selecione **Adicionar**.

    > [!NOTE]
    > Você pode selecionar todos os metadados para o aplicativo inteiro ou para modelos/módulos selecionados. Nos dois casos, os seguintes metadados serão adicionados automaticamente: tabelas de registros, enumerações e EDTs (tipos de dados estendidos). Quando tipos adicionais de metadados são necessários, eles devem ser adicionados manualmente.

    Você precisa adicionar alguns metadados que estão relacionados a transações de comércio exterior e selecionar manualmente itens de metadados.

9. Selecione **Adicionar fonte de dados \> Registros da tabela**.
10. Filtre um valor de **Intrastat** no campo **Nome**.
11. Selecione o registro de tabela **Intrastat**.
12. Selecione **OK**.

    Você precisa adicionar informações de metadados sobre a tabela de registros Intrastat.

13. Na árvore, selecione **Registros de tabela Intrastat \> \>Relações \> IntrastatCommodity (Registros de tabela EcoResCategory)**.
14. Selecione **Adicionar metadados**.

    > [!NOTE]
    > Os metadados sobre relações necessárias para a tabela selecionada de registros devem ser adicionados manualmente.

15. Selecione **Adicionar fonte de dados**.
16. Selecione **Enumeração**.
17. Filtre um valor de **IntrastatDirection** no campo **Nome**.
18. Selecione o registro de enumeração **IntrastatDirection**.
19. Selecione **OK**.
20. Selecione **Salvar**.
21. Feche a página.
22. Preencha a versão de rascunho da configuração de metadados:

    1. Selecione **Alterar status \> Concluir**.
    2. Selecione **OK**.
    3. Selecione a versão concluída 1.

23. Exporte a versão concluída da configuração de metadados do aplicativo como um arquivo XML:

    1. Selecione **Troca \> Exportar como arquivo XML**.
    2. Selecione **OK**.

A configuração de metadados de ER que você criou é salva como o arquivo **Metadados de comércio exterior.xml**. Agora você pode importá-lo para o RCS; assim, ele poderá ser usado como a fonte de metadados para o domínio comercial de comércio exterior. Com base nessas informações, você pode especificar o mapeamento entre metadados de aplicativos e o modelo de dados do ER.

## <a name="access-application-metadata-by-using-an-er-configuration"></a>Acesse metadados do aplicativo usando uma configuração do ER

O procedimento a seguir mostra como um usuário do RCS com a função de **Administrador do Sistema** ou **Desenvolvedor de Relatório Eletrônico** pode criar um novo mapeamento de modelos de ER usando metadados do aplicativo. Os metadados do aplicativo serão acessados por meio de uma configuração de metadados de ER contendo um conjunto de exemplo de metadados para acessar transações de comércio exterior.

Antes de concluir este procedimento, primeiro conclua os seguintes procedimentos:

- [Criar provedores de configuração e marcá-los como ativos](tasks/er-configuration-provider-mark-it-active-2016-11.md)
- [Preparar metadados do aplicativo que podem ser usados no RCS](#prepare-application-metadata-that-can-be-used-in-rcs)

1. Vá para **Todos os espaços de trabalho \> Relatório eletrônico**.
2. Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como **Ativo**. Se você não visualizar este provedor de configuração, conclua o procedimento [Criar provedores de configuração e marcá-los como ativos](tasks/er-configuration-provider-mark-it-active-2016-11.md). 
3. Importe a configuração de metadados de ER que contém metadados do aplicativo e que estão configurados para gerar documentos eletrônicos para o domínio comercial de comércio exterior. Você criou esta configuração de metadados de ER e exportou-a como um arquivo XML no procedimento [Preparar metadados do aplicativo que podem ser usados no RCS](#prepare-application-metadata-that-can-be-used-in-rcs) anteriormente neste tópico.

    1. Selecione **Configurações de metadados**.
    2. Selecione **Taxa de câmbio**.
    3. Selecione **Carregar do arquivo XML**.
    4. Navegue para selecionar o arquivo **Metadados de comércio exterior.xml**.
    5. Selecione **OK**.
    6. Feche a página.

4. Crie uma configuração de modelo de dados:

    1. Selecione **Configurações de relatórios**.
    2. Selecione **Criar configuração**.
    3. Na caixa de diálogo suspensa, no campo **Nome** , digite **Modelo de comércio exterior**.
    4. Selecione **Criar configuração**.
    5. Selecione **Designer**.
    6. Selecione **Novo** para abrir a caixa de diálogo suspensa.

        1. No campo **Nome**, digite **Raiz**.
        2. Selecione **Adicionar**.
    
    7. Selecione **Novo** para abrir a caixa de diálogo suspensa.

        1. No campo **Nome**, digite **Transação**.
        2. No campo **Tipo de item**, selecione **Lista de registros**.
        3. Selecione **Adicionar**.
 
    8. Selecione **Novo** para abrir a caixa de diálogo suspensa.

        1. No campo **Nome**, digite **Código de mercadoria**.
        2. No campo **Tipo de item**, selecione **String**.
        3. Selecione **Adicionar**.

    9. Selecione **Novo** para abrir a caixa de diálogo suspensa.

        1. No campo Nome, digite **Valor faturado**.
        2. No campo **Tipo de item**, selecione **Real**.
        3. Selecione **Adicionar**.

    10. Selecione **Novo** para abrir a caixa de diálogo suspensa.

        1. No campo **Nome**, digite **Data**.
        2. No campo **Tipo de item**, selecione **Data**.
        3. Selecione **Adicionar**.
 
    11. Selecione **Adicionar \> Referência raiz**.
    12. Selecione **OK**.
    13. Selecione **Salvar**.
    14. Feche a página.
    15. Selecione **Alterar status \> Concluir**.
    16. Selecione **OK**.

5. Crie uma configuração de mapeamento de modelo:

    1. Selecione **Criar configuração**.
    2. Na caixa de diálogo suspensa, no campo **Novo**, insira **Mapeamento de modelo baseado no modelo de comércio exterior de modelo de dados**.
    3. No campo **Nome**, insira **Mapeamento de comércio exterior**.
    4. Selecione **Criar configuração**.
    5. Na Guia Rápida **Pré-requisito**, selecione **Editar**.
    6. Selecione **Novo**.
    7. No campo **Tipo de componente de pré-requisito**, selecione **Configuração**.
    8. Selecione a configuração **Metadados de comércio exterior**.
    9. Selecione **Salvar**. Note que a referência foi adicionada à versão 1 da configuração de **Metadados de comércio exterior**. Os metadados de aplicativos dessa configuração serão oferecidos durante a criação do mapeamento de modelo.
    10. Feche a página.
    11. Selecione **Designer**.
    12. Selecione **Designer**.
    13. Na árvore, selecione **Dynamics 365 for Operations \> Registros de tabela**.
    14. Selecione **Adicionar raiz**.
    15. No campo **Nome**, digite **Intrastat**.
    16. Selecione registros de tabela **Intrastat**.
    17. Selecione **OK**.

        > [!NOTE]
        > Apenas duas tabelas são oferecidas porque somente duas tabelas foram adicionadas ao conjunto de metadados em uso no momento.

    18. Selecione **Associar**.
    19. Na árvore, selecione **Intrastat \> AmountMST**.
    20. Na árvore, selecione **Transação = Intrastat \> Valor faturado**.
    21. Selecione **Associar**.
    22. Na árvore, selecione **Intrastat \> TransDate**.
    23. Na árvore, selecione **Transação = Intrastat \> Date**.
    24. Selecione **Associar**.
    25. Na árvore, selecione **Intrastat \> \>Relações \> IntrastatCommodity \> Código**.
    26. Na árvore, selecione **Transação = Intrastat \> Código de mercadoria**.
    27. Selecione **Associar**.
    28. Selecione **Validar**.

        > [!NOTE]
        > Após a conclusão da validação, você associa com êxito elementos do modelo de dados a itens das fontes de dados que são descritos usando detalhes dos metadados de aplicativo da configuração de metadados de ER referenciada.

    29. Selecione **Salvar**.

Conforme necessário, você pode estender o conjunto existente de metadados no aplicativo. Depois, pode exportar a nova versão concluída da configuração de metadados de ER, importá-la para o RCS e atualizar os pré-requisitos de configuração de mapeamento de modelos configurado para referir-se a uma nova versão da configuração de metadados importada.

> [!NOTE]
> Este método de obter informações sobre os metadados do aplicativo é o único método disponível para aplicativos implantados localmente (ou seja, quando dados comerciais locais \[LBD\] ou o modelo de implantação local são usados para o aplicativo).

## <a name="access-application-metadata-by-using-connected-applications"></a>Acessar metadados do aplicativo usando aplicativos conectados

O procedimento a seguir mostra como um usuário do RCS com a função de **Administrador do Sistema** ou **Desenvolvedor de Relatório Eletrônico** pode criar um novo mapeamento de modelos de ER usando metadados do aplicativo. Os metadados do aplicativo serão acessados online usando o aplicativo conectado do RCS. O mapeamento de modelo ER de exemplo será configurado para acessar transações de comércio exterior.

Para concluir este procedimento, primeiro você deve concluir o procedimento [Criar provedores de configuração e marcá-los como ativos](tasks/er-configuration-provider-mark-it-active-2016-11.md) no RCS. Se você ainda não concluiu o procedimento [Acessar metadados do aplicativo usando a configuração ER](#access-application-metadata-by-using-an-er-configuration) antes neste tópico, vá para a página [Guias de Tarefas de Relatório Eletrônico do Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739) para baixar os seguintes arquivos de configuração de ER com antecedência e salvá-los localmente: **Metadados de comércio exterior.xml**, **Modelo de comércio exterior.xml** e **Mapeamento de comércio exterior.xml**.


### <a name="get-required-er-configurations"></a>Obtenha configurações de ER necessárias

Se você já tiver concluído o procedimento [Acessar metadados do aplicativo usando uma configuração ER](#access-application-metadata-by-using-an-er-configuration) antes neste tópico, já terá todas as configurações ER necessárias (as configurações de metadados de comércio exterior, modelo e mapeamento) na instância do RCS atual. Nesse caso, você poderá ignorar este procedimento.

1. Vá para **Todos os espaços de trabalho \> Relatório eletrônico**.
2. Selecione **Configurações de relatórios**.
3. Carregue os arquivos de configuração **Metadados de comércio exterior.xml**, **Modelo de comércio exterior.xml** e **Mapeamento de comércio exterior.xml**, repetindo a seguinte sequência de etapas para cada um deles:

    1. Selecione **Taxa de câmbio**.
    2. Selecione **Carregar do arquivo XML**.
    3. Selecione **Procurar** e selecione um arquivo.
    4. Selecione **OK**.

### <a name="register-the-connection-with-the-application"></a>Registrar a conexão com o aplicativo

1. Vá para **Todos os espaços de trabalho \> Relatório eletrônico**.
2. Selecione **Aplicativos conectados**.
3. Verifique se o aplicativo configurado baseia-se no Microsoft Azure e se está geralmente acessível para usuários no RCS. O usuário do RCS atual precisa ter acesso ao aplicativo configurado. Para isso, ele deve estar registrado como um usuário desse aplicativo em uma função que lhe conceda privilégios para acessar metadados do aplicativo.
4. Selecione **Novo**.
5. No campo **Nome**, digite **MyConnectedApp** como o nome do aplicativo associado.
6. No campo **Aplicativo**, especifique a URL do aplicativo.
7. No campo **Locatário**, especifique a provedor do aplicativo.
8. Selecione **Salvar**. 
9. Quando você verificar a conexão com o aplicativo configurado, na página **Conectar-se ao aplicativo remoto**, selecione o link **Selecione aqui para conectar-se ao aplicativo remoto selecionado**. 
10. Selecione **Verifique a conexão** para validar o acesso ao aplicativo configurado.
11. Selecione **Fechar**.

Ao concluir este procedimento e a validação da conexão for bem-sucedida, os detalhes da versão e do locatário serão atualizados para o aplicativo configurado na grade atual.

### <a name="review-the-existing-model-mapping-configuration"></a>Reveja a configuração de mapeamento do modelo existente

1. Vá para **Todos os espaços de trabalho \> Relatório eletrônico**.
2. Selecione **Configurações de relatórios**.
3. Na árvore, selecione **Modelo de comércio exterior \> Mapeamento de comércio exterior**.
4. Selecione a Guia Rápida **Pré-requisitos**.

    > [!NOTE]
    > Atualmente, o mapeamento se refere à configuração dos metadados. Os metadados de aplicativos dessa configuração serão oferecidos durante a criação do mapeamento deste modelo.

4. Selecione **Designer**.
5. Selecione **Designer**.
6. Na árvore, selecione **Dynamics 365 for Operations \> Registros de tabela**.
7. Selecione **Adicionar raiz**.
8. No campo **Tabela**, insira ou selecione um valor.

    > [!NOTE]
    > Atualmente, o mapeamento se refere à configuração dos metadados. Os metadados de aplicativos dessa configuração serão oferecidos durante a criação do mapeamento deste modelo.

9. Selecione **Cancelar**.

### <a name="assign-the-connected-application-to-a-model-mapping"></a>Atribua o aplicativo conectado a um mapeamento de modelo

1. Selecione **Editar**.
2. No campo **Aplicativo conectado**, selecione o aplicativo **MyConnectedApp** .

    > [!NOTE]
    > Este mapeamento refere-se aos metadados do aplicativo conectado selecionado. Se um mapeamento referir-se à configuração de metadados e ao aplicativo associado simultaneamente, os metadados do aplicativo conectado serão usados.

3. Selecione **Designer**.
4. Selecione **Designer**.
5. Na árvore, selecione **Dynamics 365 for Operations \> Registros de tabela**.
6. Selecione **Adicionar raiz**.
7. No campo **Tabela**, insira ou selecione um valor.

    > [!NOTE]
    > Nesse ponto, mais de duas tabelas do aplicativo são oferecidas, pois esse mapeamento utiliza todos os metadados do aplicativo conectado que foram atribuídos a ele.

8. Selecione **Cancelar**.
9. Selecione **Validar**.

Você associou elementos do modelo de dados a itens das fontes de dados que são descritos usando detalhes dos metadados do aplicativo conectado que foram atribuídos a este mapeamento.

Quando você precisar avaliar esse mapeamento de modelo usando os metadados de uma versão diferente do aplicativo, registre outro aplicativo conectado, atribua-o a este mapeamento de modelo e valide-o em relação aos novos metadados.

## <a name="additional-resources"></a>Recursos adicionais

Alternativamente, você pode executar a guia de tarefas **Preparar os metadados de aplicativo que podem ser usados no RCS** no aplicativo, bem como as guias de tarefas **Acessar metadados de aplicativos usando uma configuração de ER** e **Acessar metadados de aplicativos usando aplicativos conectados** no RCS. Essas guias de tarefas podem ser baixadas na página [Guias de tarefas de relatórios eletrônicos do Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739).
