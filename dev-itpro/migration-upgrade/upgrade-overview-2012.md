---
title: Atualizar Dynamics AX 2012 para Dynamics 365 for Finance and Operations, Enterprise Edition
description: "Este tópico descreve o processo que os clientes que atualmente executam o Microsoft Dynamics AX 2012 podem usar para mover seus dados e códigos para o Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition."
author: tariqbell
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer, IT Pro
ms.reviewer: margoc
ms.search.scope: Operations Platform
ms.search.region: Global
ms.author: tabell
ms.search.validFrom: 2017-06-16
ms.dyn365.ops.version: Platform update 8
ms.translationtype: Human Translation
ms.sourcegitcommit: 6816e3820ab77c71bbf9bde4a068375448331671
ms.openlocfilehash: 13507fcf9c0d626709aeb4e00a8632411204c20f
ms.contentlocale: pt-br
ms.lasthandoff: 06/15/2017

---

# <a name="upgrade-microsoft-dynamics-ax-2012-to-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition"></a>Atualize o Microsoft Dynamics AX 2012 para o Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition

[!include[banner](../includes/banner.md)]

Na atualização da Plataforma 8, o Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, fornece um caminho de atualização que os clientes que atualmente executam o Microsoft Dynamics AX 2012 podem usar para mover seus dados e códigos para Finanças e Operações. O processo de atualização é construído nos seguintes elementos:

- Ferramentas para ajudá-lo a divulgar o código de aplicativo personalizado existente no AX 2012.
- Um processo de atualização de dados que você pode usar para divulgar seu banco de dados. Portanto, você pode atualizar seu histórico transacional completo.

## <a name="overview"></a>Visão Geral

O processo de atualização geral pode ser visualizado como três fases principais: Analisar, Executar e Validar.

O diagrama a seguir mostra o processo de atualização de ponta a ponta e as atividades que consideramos parte de cada fase. 

![Atualizar processo](./media/upgrade-process.png)

## <a name="analyze"></a>Analisar

As atividades na fase de análise ajudam a estimar o esforço necessário para a atualização. Elas também o ajudam a preparar um plano de projeto. Essas atividades podem ser executadas antes de comprar Finanças e Operações. Eles irão ajudá-lo a tomar uma decisão de compra informada fornecendo um ponto de dados sobre o esforço e os recursos que você precisará.

### <a name="sign-up-for-a-public-preview-in-lcs"></a>Inscreva-se para uma visualização pública no LCS

Para realizar as atividades de análise antes de comprar Finanças e Operações, você pode se inscrever para uma visualização pública. A visualização pública permite que você implemente seus próprios ambientes do Finance and Operations. Ele também lhe dá acesso às ferramentas no Microsoft Dynamics Lifecycle Services (LCS) que são usadas para avaliar o seu ambiente AX 2012 e seu código personalizado existente.

Se você tem um projeto LCS existente para o AX 2012, você ainda deve se inscrever para um novo projeto adicional para avaliar Finanças e Operações.

Para obter informações sobre como obter uma visualização pública para clientes, acesse https://mbs.microsoft.com/customersource/global/AX/news-events/news/Microsoft_Dynamics_AX_Public_Preview.

Para obter informações sobre como obter uma visualização pública para parceiros, acesse https://mbs.microsoft.com/partnersource/global/news-events/news/Microsoft_Dynamics_AX_Public_Preview.

Esteja ciente de que esta visualização pública difere de uma [versão de avaliação de 30 dias](https://aka.ms/D365OperationTrials). As versões de avaliação de trinta dias fornecem uma instância implantada do Finance and Operations que você pode usar para explorar e avaliar a aplicação. No entanto, as atividades de análise requerem a experiência e as ferramentas completas do LCS.

### <a name="select-the-upgrade-methodology"></a>Selecione a metodologia de atualização
Em seu novo projeto de LCS, defina a metodologia de projeto para **Atualizar o AX 2012 para Dynamics 365 for Operations**. Esta metodologia é feita especialmente para clientes do AX 2012 que estão atualizando. Ela descreve as três fases em detalhes e fornece links para toda a documentação de suporte sobre o processo.

![Metodologia de atualização(./media/methodology.png)
 
### <a name="run-the-upgrade-analyzer"></a>Execute o analisador de atualização
A ferramenta de análise de atualização é executada em seu ambiente AX 2012 e identifica as tarefas que você deve fazer para preparar o ambiente AX 2012, para ajudar a tornar a experiência de atualização mais suave e menos dispendiosa:

- **Limpeza de dados** – Este processo ajuda a identificar os dados que você pode remover sem causar perda de funcionalidade. A ferramenta identifica vários tipos de dados que você pode reduzir executando um processo de limpeza. Para cada tipo de dados, é dada uma explicação sobre o impacto da limpeza. Você então decide se deseja executar o processo de limpeza. Parte do custo de sua assinatura do Finanças e Operações é baseado no tamanho do banco de dados. Portanto, ao reduzir o tamanho, você reduz esse componente do custo da assinatura e também ajuda a reduzir o tempo necessário para o processo de ativação da atualização. Um banco de dados menor ajuda a garantir uma atualização mais rápida.
- **Configuração do SQL** – Este processo examina a configuração do SQL e recomenda otimizações. Ao certificar-se de que o SQL funciona de forma otimizada, esse processo ajuda a reduzir o tempo necessário para o processo de ativação da atualização.
- **Recursos obsoletos** – Este processo identifica recursos que você está usando atualmente, mas que não estão disponíveis no Finance and Operations. Portanto, o processo ajuda a descobrir lacunas de funcionalidade precocemente. Ele também oferece sugestões para alternativas.

Além disso, como parte desta etapa, você deve instalar o KBXXXXXXX no ambiente do AX 2012. Este hotfix fornece uma lista de verificação pré-atualização. No ambiente do AX 2012, você pode usar esta lista de verificação para inserir dados que serão necessários para o procedimento de atualização. Por exemplo, em uma tarefa de lista de verificação pré-atualização, você fornece as informações de login do Microsoft Azure Active Directory (Azure AD) para cada usuário atual do AX 2012, para que cada usuário possa fazer login no Finanças e Operações.

O resultado desta etapa torna-se o fluxo de trabalho no plano de projeto de atualização para seus administradores de sistema AX 2012.

Para obter mais informações, consulte [Análise: Use o analisador de atualização para planejar o trabalho de migração](upgrade-analyzer-tool.md).

### <a name="run-the-code-upgrade-estimation-tools"></a>Execute as ferramentas de estimação de atualização de código
Esta etapa lê seu código do AX 2012, converte-o para o novo formato e fornece comentários sobre conflitos que o desenvolvedor deve resolver mais tarde. Esta etapa constitui a base para a estimativa do custo da atualização do seu código.

Para completar esta etapa, você deve exportar seu código do AX 2012 como exportação de uma loja modelo e enviá-lo para a ferramenta de atualização do Código LCS. A ferramenta de atualização de código produzirá uma versão atualizada do seu código e um relatório sobre os conflitos restantes que devem ser resolvidos. Seu desenvolvedor pode então revisar o código atualizado e o relatório para determinar o esforço que será necessário para atualizar sua base de código.

O resultado desta etapa representa o fluxo de trabalho no plano de projeto de atualização para seus desenvolvedores do Microsoft Dynamics AX.

Para obter mais informações, consulte [Análise: Estimar o trabalho para atualizar o código](analyze-code-upgrade.md).

### <a name="deploy-a-demo-environment"></a>Implantar um ambiente de demonstração
Os ambientes de demonstração são os ambientes padrão que contêm dados de demonstração (não seus próprios dados) e o código padrão (nenhuma personalizações). Recomendamos que você implante um ambiente de demonstração para avaliar novos recursos e para realizar uma análise básica de lacunas de ajuste de processos padrão que são usados ​​no AX 2012, mas que pode ter mudado no Finance and Operations. Você pode implantar esses ambientes de demonstração no Azure ou baixá-los como uma máquina virtual (VM) que você executa em seu próprio hardware. Se você implantá-los no Azure, você deve fornecer sua assinatura do Azure, porque você ainda está usando um projeto de pré-visualização público e ainda não adquiriu uma assinatura do Finance and Operations.

O resultado desta etapa representa o fluxo de trabalho no plano de projeto de atualização para seus usuários funcionais ou usuários corporativos.

Para obter mais informações, consulte [Análise: Implantar um ambiente do sandbox](analysis-sandbox.md)

### <a name="create-a-project-plan"></a>Criar um plano de projeto
Um modelo para um plano de projeto é fornecido na metodologia de atualização. Nesta etapa, o resultado das etapas anteriores da fase de análise é usado para preencher o plano do projeto para o projeto de atualização. O plano do projeto também conterá todos os detalhes de teste: teste de atualização de dados, testes de fechamento, as avaliações de passagens de teste funcional e detalhes sobre as várias atribuições de recursos para essas tarefas.

Nesta fase, o plano do projeto fornece um ponto de dados que pode ajudá-lo a entender o tempo e o custo que uma atualização para Finanças e Operações envolverá.

## <a name="execute"></a>Executar
Durante a fase de execução, você trabalha com as tarefas que você planejou durante a fase de análise. Para passar para a fase de execução, você deve comprar Finanças e Operações, e você deve ter recursos disponíveis que possam funcionar na atualização.

### <a name="switch-to-the-lcs-implementation-project"></a>Mude para o projeto de implementação de LCS
O projeto de pré-visualização público que você usou para a fase de análise atendeu à sua finalidade. Agora você pode rejeitá-lo. Para as etapas restantes, você precisa apenas do plano de projeto que você criou na etapa final da fase de análise.

Quando você adquire uma assinatura do subscrição do Finanças e Operações, você receberá detalhes sobre como se inscrever em um novo projeto de LCS. Este projeto é conhecido como um projeto de implementação e será o novo projeto de LCS permanente para sua assinatura, desde que você tenha essa assinatura. Este projeto difere do projeto de visualização público na medida em que é gerenciado pela Microsoft. Portanto, esse projeto tem as seguintes características:

- Todos os ambientes do projeto estão hospedados no Azure.
- A assinatura do Azure associada ao projeto é gerenciada pela Microsoft. Portanto, não há cobrança separada para os custos do Azure. Os custos são cobertos pela sua assinatura do Finance and Operations.
- O ambiente de produção no projeto é mantido pela Microsoft. Portanto, implementações de código, atualizações e manutenção de infraestrutura são executadas diretamente pela Microsoft, não por sua equipe. 

### <a name="perform-the-ax-2012-preparation-tasks"></a>Execute as tarefas de preparação do AX 2012
Complete as tarefas que a ferramenta de análise de atualização descobriu e que estão documentadas em seu plano de projeto de atualização. O administrador do sistema e o administrador de banco de dados (DBA) do Microsoft Dynamics AX devem completar essas tarefas.

[Atualização de dados do AX 2012 para Dynamics 365 for Operations – Lista de verificação da pré-atualização no AX 2012](prepare-data-upgrade.md)

### <a name="perform-code-upgrade"></a>Executar atualização de código
Complete as tarefas que foram planejadas durante a etapa de estimativa de atualização de código da fase de análise. Os desenvolvedores devem executar essas tarefas.

A partir deste ponto, as mudanças de código no AX 2012 devem ser congeladas. Somente alterações de código de emergência devem ser permitidas no AX 2012. Se uma alteração for feita, ela deve ser portada manualmente para a nova base de código.

### <a name="develop-new-code"></a>Desenvolva o novo código
Complete as tarefas a partir da análise de lacunas de ajuste que foi realizada durante a etapa "Implementar um ambiente de demonstração" da fase de análise. Essas tarefas provavelmente serão uma mistura de tarefas funcionais que definem as tarefas de configuração e desenvolvimento para personalizações relacionadas a novos recursos que estão sendo ocupados.

### <a name="data-upgrade-development-environment"></a>Atualização de dados (ambiente de desenvolvimento)
Depois que suas tarefas de atualização de código estiverem concluídas, você pode atualizar o seu banco de dados AX 2012 para Finanças e Operações pela primeira vez. Esta primeira atualização ocorre em um ambiente de desenvolvimento, para que você possa corrigir ou depurar todos os problemas encontrados nesta fase com mais facilidade. Em um ambiente de desenvolvimento, um problema pode ser depurado imediatamente, o código pode ser ajustado, e a atualização pode ser executada novamente em minutos. Ambientes de sandbox maiores não oferecem essa agilidade, e um mínimo de várias horas será necessário para depurar e corrigir problemas, atualizar o código, implantar o código atualizado e executar novamente a atualização.

A ilustração a seguir mostra o processo. Basta fazer backup do banco de dados do AX 2012, enviá-lo para o Azure, restaurá-lo para o ambiente do Finance and Operations e, em seguida, executar a atualização de dados.

![Atualização de dados em um ambiente de desenvolvimento](./media/data-upgrade-dev.png)
 
A atualização de dados é feita através de um tipo especial de pacote implantável. O mesmo mecanismo é usado para implantar o novo código do Finance and Operations de um ambiente para outro ambiente.

A estrutura subjacente que é usada para converter os dados no banco de dados durante este processo é em grande parte a mesma que a estrutura de atualização no AX 2012 que é baseada em trabalhos em lote X++ que executam classes **ReleaseUpdatexxx**.

Para obter detalhes, consulte [Atualização de dados do AX 2012 para o Dynamics 365 for Operations em um ambiente de desenvolvimento](data-upgrade-2012.md).

### <a name="data-upgrade-sandbox-environments"></a>Atualização de dados (ambientes do sandbox)
Quando a atualização de dados em um ambiente de desenvolvimento é concluída, o mesmo processo pode ser executado em um ambiente sandbox. O ambiente sandbox é o ambiente em que os usuários corporativos e os membros da equipe funcional podem testar os processos comerciais usando os dados e o código atualizados do AX 2012.

A ilustração a seguir mostra o processo para executar a atualização de dados em um ambiente sandbox. A diferença aqui é que a ferramenta bacpac é usada em vez de um backup SQL tradicional. Esta ferramenta é necessária para converter entre o Microsoft SQL Server e o banco de dados de Azure SQL. É uma ferramenta padrão SQL, e não é específica do Finanças e Operações.

![Atualização de dados em um ambiente sandbox](./media/data-upgrade-sandbox.png)

Para obter detalhes, consulte [Atualização de dados do AX 2012 para o Dynamics 365 for Operations em um ambiente sandbox](upgrade-data-sandbox.md).
 
## <a name="validate"></a>Validar
Quando você entrar na fase de validação, você terá ambientes disponíveis que incluem seu código personalizado atualizado e seus dados atualizados. Esta fase descreve o processo de validação e teste que o ambiente atualizado executa conforme desejado. Ele também descreve o processo de preparação para a ativação.

### <a name="perform-cutover-testing-and-create-a-cutover-plan"></a>Execute testes de fechamento e crie um plano de fechamento
O termo _fechamento_ é usado aqui para descrever o processo final de ativação do novo sistema. Esse processo consiste nas tarefas que ocorrem após o AX 2012 estar desativado e antes do Finance and Operations estar ativado. 

O objetivo do teste é praticar o processo de fechamento. Desta forma, você pode ajudar a garantir que todos os que estão envolvidos no fechamento real para ativação terão uma boa experiência.

Há dois fluxos de trabalho principais:

- **Fluxo de trabalho técnico** – Este fluxo de trabalho é o processo de execução da atualização de dados. Sua empresa aplicará um limite na quantidade de tempo de inatividade permitido. Durante este período de inatividade, nem o AX 2012 nem Finanças e Operações estarão disponíveis. O fluxo de trabalho técnico pode ter que ajustar o desempenho do seu procedimento de atualização de dados para atender ao limite de tempo de inatividade da empresa. 
- **Fluxo de trabalho funcional** – Após a atualização de dados, serão necessárias várias tarefas de configuração no ambiente do Finance and Operations. Todas essas tarefas devem ser documentadas e quantificadas, e um recurso deve ser atribuído a elas, porque elas devem se encaixar com as tarefas técnicas dentro do limite de tempo de inatividade da empresa.

Para obter detalhes, consulte 
- [Validar: Teste de fechamento](upgrade-cutover-testing.md)
- [Validar: Processo de validação de aplicativo](app-validation-process.md)

### <a name="functional-test-pass"></a>Passagem de teste funcional
Concluir uma passagem de teste funcional total de todos os processos comerciais. Essa passagem de teste será um novo teste extensivo de todos os processos que envolvem Finanças e Operações. Esses processos de negócios incluem processos antigos que foram trazidos do AX 2012 e processos novos que envolvem os novos recursos que foram aceitos pela primeira vez no Finance and Operations. 

Dependendo da qualidade do código, a remediação de problemas e o novo teste podem exigir várias iterações da passagem de teste funcional. Quando um problema for corrigido, certifique-se de repetir todos os processos envolvidos, para garantir que o processo upstream ou downstream não seja afetado pela alteração.

Para obter detalhes, consulte [Validar: Testes funcionais](upgrade-functional-validation.md).

### <a name="pre-go-live-checklist"></a>Lista de verificação de pré-ativação
A lista de verificação de pré-ativação é um procedimento recomendado que pode ajudar a reduzir a chance de erros durante o fechamento para a ativação. Uma semana antes do início da ativação pare as mudanças de configuração no AX 2012 (ou seja, em \<módulo\>\Configuração). Essa restrição nas alterações de configuração é meramente processual. Os administradores de sistema do Microsoft Dynamics AX apenas concordam em colocar as mudanças deste tipo em espera neste momento.

Recomendamos que você também congele alterações de código na base do código do Finanças e Operações. Nenhuma outra alteração deve ser permitida, a menos que tenham sido avaliadas, e mostraram que não bloqueiam a ativação.  

Depois que a restrição de configuração e o congelamento de código estiverem instalados, a atualização de dados deve ser executada pela última vez antes do fechamento. Desta forma, você pode ter certeza de que tudo ainda funciona conforme o esperado. 

Para obter detalhes, consulte [Validar: Preparar para ativar](upgrade-go-live-prep.md).



### <a name="supported-upgrade-paths"></a>Caminhos de atualização suportados
A partir de junho de 2017, a atualização para o Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, versão 0617 é suportada pelo Microsoft Dynamics AX 2012 R3. Todas as atualizações cumulativas (CUs) do AX 2012 R3 são suportadas.

O Microsoft Dynamics AX 2012 R2 e o Microsoft Dynamics AX 2012 RTM não são suportados atualmente. O suporte será adicionado posteriormente em 2017.

Somente a atualização para a versão implementada na nuvem do Finanças e Operações é suportada. A atualização para a versão local não é suportada. O suporte para atualização para a versão local será adicionado no final de 2017.

