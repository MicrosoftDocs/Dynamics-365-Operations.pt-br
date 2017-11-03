---
title: "Exibição e criação de relatórios financeiros"
description: "Este artigo fornece exercícios que o conduzem pela exibição e criação de relatórios financeiros do Microsoft Dynamics 365 for Finance and Operations."
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 10814
ms.assetid: cd5f6483-c09b-4c2d-9336-d22eb6ab6e4f
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: b49cfe39732a450e4723419c50d8bcc3d64b7ec9
ms.openlocfilehash: d1fbcefd80f1c48fafbbcb6315406856eaae68a0
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="view-and-design-financial-reports"></a>Exibição e criação de relatórios financeiros

[!include[banner](../includes/banner.md)]


Este artigo fornece exercícios que o conduzem pela exibição e criação de relatórios financeiros do Microsoft Dynamics 365 for Finance and Operations. Os relatórios financeiros consistem de uma experiência de exibição no Finance and Operations e o designer de relatórios de clique único que permite que você crie e edite relatórios financeiros.  

<a name="exercise-1-generate-and-explore-a-default-financial-report"></a>Ano 1: Gerenciar e explorar um relatório financeiro padrão
-----------------------------------------------------------

Para este ano, você estará gerando e explorando um relatório padrão. Este relatório inclui todas as contas e também contém as propriedades da conta (atributos) para as contas. Você poderá fazer buscas nos detalhes da transação, aplicando filtros de dimensão, alterando a moeda no relatório. Primeiro, a ordem de exibição das dimensões para os relatórios financeiros serão atualizados. Isso permite escolher como as dimensões são exibidas não só ao criar e visualizar os relatórios financeiros.

1.  Vá para **Configuração da dimensão financeira para integrar aplicativos** nas **Dimensões do plano de contas** na contabilidade.
2.  Mova as dimensões para a seguinte ordem:
    1.  Conta principal
    2.  Unidade de negócios
    3.  Centro de custos
    4.  Departamento

    Observação: As outras dimensões podem permanecer na ordem em que estão.
3.  Salve a configuração da dimensão. Em seguida, geraremos um relatório e exploraremos os dados no relatório.
4.  Vá para **Relatórios financeiros** em **Consultas e relatórios** na contabilidade.
5.  Selecione a linha do relatório chamado **Detalhe de contabilidade – Padrão.**
6.  Selecione **Editar.** Nota: Será solicitado que você baixe o criador de relatórios de clique único e faça logon. Use suas credenciais para fazer logon.
7.  Altere o ano de base para 2012 e selecione **Gerar**. Quando um relatório é gerado do designer de relatórios, ele é aberto em uma nova guia do navegador. Também é possível explorar o relatório na nova guia do navegador ou ir para a guia do navegador original e abrir o relatório de lá, selecionando-o da lista **Relatórios financeiros**.
8.  No relatório aberto, selecione um dos valores para ser detalhado no detalhe da conta do relatório.
9.  Nos detalhes da conta, selecione uma conta com dados e **detalhe o nível de transação do relatório**. No nível da transação do relatório, você pode ver as propriedades (atributos) que estão incluídas na criação do relatório. Dependendo da transação e da conta, alguns ou todos os atributos podem ser exibidos.
10. Feche o nível da transação do relatório.
11. Selecione a mesma ou uma conta diferente e **abra as transações do comprovante.** As transações de comprovante são filtradas por período, ano e conta + combinação da dimensão da conta selecionada. Nas transações de comprovante, é possível explorar outras informações sobre a transação.
12. Feche as transações do comprovante. Dentro de um relatório financeiro, você pode exibir os dados para um período e um ano diferentes ou com atributos diferentes e as dimensões aplicados. Isso é feito ao usar as **Opções do relatório**.
13. Selecione **Opções do relatório**.
14. Selecione **Adicionar um filtro de dimensão** e escolha **Unidade de negócios**.
15. Digite 001 no campo e selecione **OK**. Agora, o relatório só exibe os dados para a Unidade de negócios 001. Esta é uma visualização personalizada do relatório e não está disponível para outras pessoas.
16. Feche o relatório filtrado. Os relatórios financeiros podem ser exibidos em qualquer moeda que foi adicionada ao Finance and Operations.
17. Selecione **Moeda** e selecione **EUR.** E novo relatório é exibido em Euro. Agora, todos os códigos ou símbolos de moeda incluídos na criação do relatórios são exibidos na moeda aplicada. Se nenhum símbolo de moeda for definido, o símbolo da moeda não será exibido.
18. Feche o relatório **Detalhes de contabilidade**.
19. Feche o **Criador de relatórios**.

## <a name="exercise-2-add-additional-account-properties-to-a-report-design"></a>Ano 2: Adicione as propriedades da conta adicionais a um design de relatório
Neste exercício, você modificará um relatório padrão existente. Você atualizará a definição de linha para incluir todas as contas e atualizará a definição da coluna para conter os atributos da conta. Depois que as atualizações forem concluídas, você gerará um relatório recém-criado e explorarão o relatório. Nós iniciaremos na lista de relatórios financeiros.

1.  Vá para **Relatórios financeiros** em Consultas e relatórios na contabilidade.
2.  Selecione a linha para o relatório chamado **Resumo do balanço – Padrão**
3.  Selecione **Editar**. O **Resumo do balancete resumida – Padrão** será aberto no criador de relatórios
4.  Selecione **Arquivo** e **Salvar como** e nomeie o relatório Balancete detalhado com Atributos. Nota: Sempre que um novo relatório é criado no designer de relatórios, a lista de relatórios financeiros é atualizada no Finance and Operations.
5.  Na definição do relatório, selecione o ícone de definição da linha para abrir a **definição da linha Balancete - Padrão**.
6.  Salvar a definição da linha como **Balancete detalhado com atributos**
7.  Com o cursor na linha 50, selecione **Editar** e **Inserir linhas nas dimensões**. As linhas de inserção de dimensões permite escolher quais dimensões deseja de ter na definição de linha. Para este ano, vamos criar a definição da linha usando a conta principal.
8.  Verifique se **Conta principal** contém todos os E comerciais e selecione **OK**. Agora, uma nova definição contém todas as contas principais para a USMF de entidade legal.
9.  Role para baixo para enfileirar 11110 e exclua a linha 11110.
10. Na linha 11080, selecione **--- (Valores sublinhados)**.
11. Na linha 11140, digite **Total de todas as contas** na coluna B.
12. Na coluna c, selecione **TOT** no menu suspenso.
13. Digite **50:11080** na coluna D.
14. **Salve** a definição da linha. Agora, a definição da linha contém todas as contas mais uma linha total para agrupar todas as contas. Em seguida, a definição de colunas será atualizada para incluir os atributos adicionais da conta.
15. Na definição de relatório **Balancete detalhado com atributos**, selecione o ícone da definição da coluna para abrir a definição da coluna **Resumo do balancete – Padrão**.
16. Salve a definição da coluna como **Balancete detalhado com atributos** A definição da coluna contém colunas de dados financeiros, como uma coluna de descrição e de cálculos. As colunas de atributos serão adicionadas à definição da coluna para fornecer detalhes adicionais sobre as contas.
17. Os atributos a seguir serão adicionados à definição da coluna:
    -   Número do diário
    -   Descrição do diário
    -   Data da Transação
    -   Criado por
    -   Última modificação por

18. Na coluna I, selecione **ATTR** como o tipo de coluna. Em seguida, selecione **Número do razão** como a categoria do atributo.
19. Continue adicionando colunas para os demais atributos.
20. Na linha **Cabeçalho 2**, adicione descrições para cada uma das novas colunas adicionadas.
21. Salve a definição da coluna. Agora que as definições da linha e da coluna foram atualizadas, será necessário adicioná-las à definição de relatórios.
22. Na definição de relatório **Balancete detalhado com atributos**, selecione Balancete detalhado com atributos para as definições da linha e de coluna.
23. Alterar o ano base para **2012.**
24. **Salvar** a definição de relatório e **gerar**. Depois de concluir a geração dos relatórios e de abri-los, é possível explorar o relatório, como foi feito no primeiro ano. Fazer busca detalhada em contas diferentes para ver como os atributos adicionais serão exibidos.
25. Feche o relatório **Balancete detalhado com atributos**.
26. Feche o **Criador de relatórios**.

## <a name="exercise-3-create-a-multidimensional-report-using-a-reporting-tree"></a>Exercício 3: Criar um relatório multidimensional usando uma árvore de relatórios
Para este ano, você modificará um relatório padrão existente. Você criará uma árvore de relatórios e adicionará a uma definição de relatórios para produzir um demonstrativo do centro de custo/entrada por divisão. Depois de concluir as atualizações, você gerará um demonstrativo do centro de custo e da entrada por divisão e explorará o relatório usando a árvore de relatórios. Nós iniciaremos na lista de relatórios financeiros.

1.  Vá para **Relatórios financeiros** em Consultas e relatórios na contabilidade.
2.  Selecione a linha do relatório chamada **Demonstrativo de renda – Padrão**
3.  Selecione **Editar**. O **Demonstrativo de renda – Padrão** será aberto no criador de relatórios.
4.  No menu **Arquivo**, posicione o cursor em **Novo** e clique em **Definição da árvore de relatórios**
5.  No menu **Editar**, clique em **Inserir unidades de relatórios de dimensões**…
6.  Limpar caixas de seleção para todas as dimensões, exceto **Centro de custos**.
7.  Clique no campo **Da dimensão** para a dimensão do centro de custos, digite **007** e pressione a tecla TAB. No campo **Para dimensão**, digite **018**.
8.  **Salve** a árvore resultante com o nome **Centros de custo por divisão.** Agora que a árvore do relatório foi criada, você alterará a árvore de relatórios para conter três novas unidades de acúmulo; Marketing, Operações e Varejo.
9.  No menu **Visualizar**, clique em **Centros de custo por divisão**. (Se a árvore do relatório foi fechada, selecione-a nas Definições de árvore de relatórios no painel de navegação.)
10. Clique na unidade número dois **Feiras profissionais** e clique no ícone **Inserir unidade de relatórios**.
11. Clique duas vezes na coluna da entidade na linha em branco, e selecione **USMF**.
12. Digite **Mercado** nas colunas B e C.
13. Clique na unidade número cinco, **Operações de serviço** e clique com o botão direito. **Selecione Inserir unidade de relatórios**.
14. Repita a etapa 11.
15. Digite **Operações** nas colunas B e C.
16. Clique na unidade número doze, **Loja** e clique com o botão direito. Selecione **Inserir unidade de relatórios**.
17. Repita a etapa 11.
18. Digite **Varejo** nas colunas B e C. Observe que as unidades Marketing, Vendas, Operações e Varejo são exibidas no mesmo nível das unidades de acúmulo atuais. As novas unidades são organizadas em seguida. As unidades de relatório são organizadas com as opções clique com o botão direito do mouse; promover e rebaixar ou arrastar e soltar.
19. Verifique se a unidade, **Feiras profissionais** está ativa e clique com o botão direito do mouse.
20. Selecione **Rebaixar unidade de relatórios**. Observa que, agora, a unidade é exibida como filho de **Marketing**.
21. Clique em unidade quatro, **Marketing** **Campanha** e clique com o botão direito.
22. Selecione **Rebaixar unidade de relatórios**.
23. Clique em **Operações de serviço** na exibição gráfica. Pressione e mantenha pressionada o botão esquerdo do mouse ao arrastar a unidade até **Operações**. Solte o botão esquerdo para soltar a unidade no acúmulo de Operações. Repita para **Produção, controle de qualidade, logística, itens e administração**.
24. Defina **Loja**, **Super**, **Shopping** and **On-line** filhos de **Varejo** ao rebaixá-los ou ao arrasta-los e soltá-los.
25. Salvar o resultado e a reorganização. Agora que a árvore de relatórios foi criada e organizada, ela pode ser adicionada à definição de relatórios.
26. No menu **Janela**, selecione **Demonstrativo de renda – Padrão** para abrir a definição do relatório.
27. Clique no menu suspenso **Tipo de árvore** e selecione **Árvore de relatório**.
28. Clique no menu suspenso de árvore e selecione **Centros de custo por divisão**.
29. Altere o ano base para **2012**, **salve** as alterações e **gere** o relatório. Depois que a geração do relatório for concluída e ele for aberto, é possível explorar o relatório.
30. Selecione o menu suspenso **Árvore do relatório** para visualizar as unidades de relatórios. Como alternativa, você pode fazer uma busca detalhada em uma linha do relatório para ver todos os saldos para todas as unidades da árvore de relatórios.
31. Feche **Demonstrativo de renda – Padrão**.
32. Feche o **Criador de relatórios**.

## <a name="exercise-4-create-a-consolidated-report-using-an-organization-hierarchy"></a>Ano 4: Criar um relatório consolidado usando uma hierarquia da organização
Para este ano, você modificará um relatório padrão existente. Você adicionará uma hierarquia da organização na definição de relatório para produzir um Demonstrativo de receita consolidada e um Balancete. Depois de concluir as atualizações, você gerará um relatório consolidado e explorar o relatório usando uma árvore de relatórios. Nós iniciaremos na lista de relatórios financeiros.

1.  Vá para **Relatórios financeiros** em Consultas e relatórios na contabilidade.
2.  Selecione a linha para o relatório chamado **Balancete e Demonstrativo de renda lado a lado - Padrão**
3.  Selecione **Editar**. **Balanço e demonstrativo de renda lado a lado – Padrão** será aberto no criador de relatórios.
4.  Selecione **Arquivo** &gt; **Salvar como** e nomeie o relatório **Balanço consolidado e o demonstrativo de renda lado a lado**.
5.  Alterar o ano base para 2012.
6.  Clique no menu suspenso de árvore e selecione **Hierarquias da organização**.
7.  Clique no menu suspenso de árvore e selecione **Retenções da Contoso.**
8.  Salve as alterações e gere o relatório. Se solicitado, selecione todas as unidades de relatório. Depois que a geração do relatório for concluída e ele for aberto, é possível explorar o relatório.
9.  Selecione **Opções do relatório**.
10. Selecione **Adicionar filtro da dimensão** e escolha **Departamento**.
11. Digite **022** no campo e selecione **OK**.
12. Feche o relatório filtrado.
13. Selecione o menu suspenso Árvore de relatório**s** para visualizar as unidades de relatórios. Como alternativa, você pode fazer uma busca detalhada em uma linha do relatório para ver todos os saldos para todas as unidades da árvore de relatórios.
14. Fechar **Balanço consolidado e o demonstrativo de renda lado a lado**.
15. Feche o **Criador de relatórios**.

## <a name="exercise-5-create-a-sidebyside-departmental-report"></a>Exercício 5: Criar relatório do departamento lado a lado
Neste exercício, você criará um novo relatório. O relatório é um demonstrativo de rendimentos dos departamentos lado a lado. Você usará uma definição de linha existente, mas criará uma nova definição de relatório e uma nova definição de coluna que usa filtros de dimensão. Nós iniciaremos na lista de relatórios financeiros.

1.  Vá para **Relatórios financeiros** em Consultas e relatórios na contabilidade.
2.  Selecione **Novo**. O criador de relatórios será aberto com uma definição do relatório em branco. Sua primeira tarefa será criar a definição da coluna.
3.  Crie uma nova definição da coluna ao clicar em **Arquivo**, **Novo** e em **Definição da coluna**.
4.  Na **Coluna A**, selecione **DESC** para o tipo de coluna.
5.  Na **Coluna B**, selecione **FD** para o tipo de coluna.
6.  Clique duas vezes no campo **Filtro da dimensão**.
7.  Na janela **Dimensão**, clique duas vezes na coluna **Departamento**.
8.  Na seção Individual ou intervalo da caixa de diálogo, clique no campo de **reticências** para o campo **De** para exibir uma lista de departamentos.
9.  Selecione o departamento **022**, **Vendas e marketing** e clique em **OK**.
10. Repita as etapas de 5 para 8 para os departamentos 23-25.
11. Na linha **Cabeçalho 2** para todas as colunas FD, digite as descrições do departamento a seguir:
    -   Coluna B – Vendas e Marketing
    -   Coluna C – Operações
    -   Coluna D - Financeiro
    -   Coluna E - IT

12. Salve a definição da coluna como Departamentos lado a lado. Como estamos usando uma definição de linha existente, a definição do relatório pode ser modificada para a definição da coluna criada mais recentemente e a definição de linha existente.
13. No menu **Janela**, selecione **Nova definição do relatório** para abrir a definição do relatório.
14. Selecione **Demonstrativo de renda – Padrão** como a definição da linha e **Departamentos lado a lado** como a definição de coluna.
15. Salve a definição do relatório como **Demonstrativo da receita do departamento lado a lado**.
16. Altere o ano base para **2012**.
17. Altere o nível de detalhes para **Financeiro, Conta e Transação**.
18. **Salve** suas alterações e **gere**. Depois que a geração do relatório for concluída e ele for aberto, é possível explorar o relatório.

## <a name="additional-resources"></a>Recursos adicionais
[Relatório financeiro](../../financials/general-ledger/financial-reporting-getting-started.md) 
[Exibir relatórios financeiros](../../financials/general-ledger/view-financial-reports.md) 
[Blog de Relatório Financeiro do Dynamics](http://blogs.msdn.com/b/dynamics_financial_reporting/)




