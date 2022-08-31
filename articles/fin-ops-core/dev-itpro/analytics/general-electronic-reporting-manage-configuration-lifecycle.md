---
title: Gerenciar o ciclo de vida da configuração de Relatório eletrônico (ER)
description: Este artigo descreve como gerenciar o ciclo de vida de configurações de Relatórios Eletrônico (ER) para o Dynamics 365 Finance.
author: kfend
ms.date: 07/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58801
ms.assetid: 35ad19ea-185d-4fce-b9cb-f94584b14f75
ms.search.form: ERDataModelDesigner, ERMappedFormatDesigner, ERModelMappingDesigner, ERModelMappingTable, ERSolutionImport, ERSolutionTable, ERVendorTable, ERWorkspace
ms.openlocfilehash: 0209679c9882d87edab68d043fba9e7b3400a2a2
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9337186"
---
# <a name="manage-the-electronic-reporting-er-configuration-lifecycle"></a>Gerenciar o ciclo de vida da configuração de Relatório eletrônico (ER)

[!include [banner](../includes/banner.md)]

Este artigo descreve como gerenciar o ciclo de vida de configurações do [Relatório eletrônico](general-electronic-reporting.md) (ER) [para o](general-electronic-reporting.md#Configuration) Dynamics 365 Finance.

## <a name="overview"></a>Visão geral

O relatório eletrônico (ER) é um mecanismo que oferece suporte a documentos eletrônicos específicos do país/região e exigidos pela regulamentação. Geralmente, o ER considera uma capacidade de executar as seguintes tarefas para um único documento eletrônico. Para obter mais detalhes, consulte [Visão geral de ER (Relatórios eletrônicos)](general-electronic-reporting.md).

- Projete um modelo para um documento eletrônico:

    - Identifique as fontes de dados necessárias que podem ser apresentadas no documento:

        - Os dados subjacentes, como tabelas de dados, entidades de dados e classes.
        - Propriedades específicas do processo, como data e hora da execução e fuso horário.
        - Parâmetros de entrada do usuário, especificados pelo usuário final em tempo de execução.

    - Defina os elementos do documento necessários e a topologia deles para especificar o formato de um documento final.
    - Configure o fluxo de dados desejado das fontes de dados selecionadas para elementos do documento definido via associações da fonte de dados aos componentes de formato do documento e especifique a lógica de controle de processos.

- Crie um modelo disponível de forma que ele possa ser usado em outras instâncias:

    - Transforme um modelo de documento criado em uma configuração de ER e exporte a configuração da instância atual do aplicativo como um pacote XML que possa ser armazenado localmente ou no Lifecycle Services (LCS).
    - Transforme uma configuração de ER em um modelo de documento do aplicativo.
    - Importe um pacote XML armazenado localmente ou em LCS para a instância atual.

- Personalize o modelo de um documento eletrônico:

    - Traga um modelo de LCS para a instância atual como uma configuração de ER.
    - Crie uma versão personalizada de uma configuração do ER e mantenha uma referência à versão base.

- Integre um modelo a um processo comercial específico, para que ele fique disponível no aplicativo:

    - Defina as configurações para que o aplicativo comece a usar uma configuração de ER ao fazer referência a essa configuração em um parâmetro relacionado ao processo Por exemplo, mencione a configuração de ER em um método Pagamento de contas a pagar específico para gerar uma mensagem de pagamento eletrônico para o processamento de faturas.

- Use um modelo em um processo de negócios específico:

    - Executar uma configuração de ER em um processo comercial específico. Por exemplo, para gerar uma mensagem de pagamento eletrônico para o processamento de faturas quando um método de pagamento que faz referência à configuração de ER é selecionado.

## <a name="concepts"></a>Conceitos
As funções e as atividades relacionadas a seguir estão associadas ao ciclo de vida de configuração de ER.

| Função                                       | Atividades                                                      | Descrição |
|--------------------------------------------|-----------------------------------------------------------------|-------------|
| Consultor funcional de relatório eletrônico | Crie e gerencie componentes de ER (modelos e formatos).           | Um executivo, que projeta modelos de dados específicos de domínio de ER, cria os modelos necessários para documentos eletrônicos e os associa adequadamente. |
| Desenvolvedor de relatório eletrônico             | Crie e gerencie mapeamentos de modelo de dados.                          | Um especialista que seleciona as fontes de dados do Finance necessárias e as associa aos modelos de dados específicos de domínio de ER. |
| Supervisor de contabilidade                      | Defina as configurações relacionadas ao processo que fazem referência a artefatos de ER. | Por exemplo, uma função **Supervisor de contabilidade** que permite que as configurações de uma configuração de ER sejam usadas em um método de pagamento específico de Contas a pagar para gerar uma mensagem do pagamento eletrônico para processar faturas. |
| Auxiliar de pagamentos de contas a pagar            | Use artefatos de ER em um processo de negócios específico.                | Por exemplo, uma função **Auxiliar de pagamentos de contas a pagar** que permite que as mensagens do pagamento eletrônico sejam geradas para processar faturas com base no formato de ER configurado para um método de pagamento específico. |

## <a name="er-configuration-development-lifecycle"></a>Ciclo de vida de desenvolvimento de configuração de ER
Pelos seguintes motivos relacionados a ER, é recomendável projetar configurações de ER no ambiente de desenvolvimento como uma instância separada de finanças e operações:

- Os usuários nas funções **Desenvolvedor de relatório eletrônico** ou **Consultor funcional de relatório eletrônico** podem editar configurações e executá-las para fins de teste. Este cenário pode ocasionar chamadas de métodos de classes e de tabelas que podem prejudicar os dados de negócios e o desempenho do uso da instância.
- As chamadas de métodos de classes e de tabelas como fontes de dados de ER das configurações do ER não serão restringidas por pontos de entrada e pelo conteúdo registrado da empresa. Portanto, os dados de negócios confidenciais podem ser acessados pelos usuários que desempenham a função **Desenvolvedor de relatório eletrônico** ou **Consultor funcional de relatório eletrônico**.

As configurações de ER criadas no ambiente de desenvolvimento podem ser [carregadas](#data-persistence-consideration) no ambiente de teste da avaliação da configuração (integração adequada do processo, exatidão de resultados e desempenho) e do controle de qualidade, como exatidão dos direitos de acesso orientados a funções e diferenciação de direitos. Os recursos que permitem a troca de configuração de ER podem ser usados com essa finalidade. As configurações de ER comprovadas podem ser carregadas no LCS para compartilhá-las com assinantes de serviço ou podem ser [importadas](#data-persistence-consideration) para o ambiente de produção para uso interno.

![Ciclo de vida da configuração de ER.](./media/ger-configuration-lifecycle.png)

## <a name="data-persistence-consideration"></a>Consideração de persistência de dados

Você pode [importar](tasks/er-import-configuration-lifecycle-services.md) individualmente versões diferentes de uma [configuração](general-electronic-reporting.md#Configuration) ER para sua instância do Finance. Quando uma nova versão de uma configuração ER é importada, o sistema controla o conteúdo da versão de rascunho dessa configuração:

- Quando a versão importada for anterior à versão mais atual dessa configuração na instância atual do Finance, o conteúdo da versão de rascunho dessa configuração permanecerá inalterado.
- Quando a versão importada for mais atual do que outras versões dessa configuração na instância atual do Finance, o conteúdo da versão importada será copiado para a versão de rascunho dessa configuração para que você continue editando a última versão concluída.

Se essa configuração pertencer ao [provedor](general-electronic-reporting.md#Provider) de configuração ativado no momento, a versão de rascunho dessa configuração ficará visível na FastTab **Versões** da página **Configurações** (**Administração organizacional** > **Relatório eletrônico** > **Configurações**). Você pode selecionar a versão de rascunho da configuração e [modificar](er-quick-start2-customize-report.md#ConfigureDerivedFormat) o conteúdo usando o designer de ER relevante. Após você editar a versão de rascunho de uma configuração ER, o conteúdo não coincidirá mais ao conteúdo da versão mais atual dessa configuração na instância atual do Finance. Para evitar a perda de alterações, o sistema exibe um erro informando que a importação não pode continuar porque a versão dessa configuração é posterior à versão mais atual dessa configuração na instância atual do Finance. Quando isso ocorre, por exemplo, com a configuração de formato **X**, o erro **A versão de formato 'X' não foi concluída** é exibido.

Para desfazer as alterações apresentadas na versão de rascunho, selecione a versão concluída mais atual ou compartilhada da configuração ER no Finance na FastTab **Versões** e, depois, selecione a opção **Obter esta versão**. O conteúdo da versão selecionada é copiado na versão de rascunho.

## <a name="applicability-consideration"></a>Consideração de aplicabilidade

Ao criar uma versão de uma configuração ER, você pode definir sua [dependência](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md) em outros componentes de software. Essa etapa é considerada um pré-requisito para controlar o download desta versão da configuração de um repositório de ER ou um arquivo XML externo, e para qualquer outro uso da versão. Ao tentar importar uma nova versão de uma configuração ER, o sistema usa os pré-requisitos configurados para controlar se a versão pode ser importada.

Em alguns casos, você pode exigir que o sistema ignore os pré-requisitos configurados ao importar novas versões das configurações ER. Para que o sistema ignore os pré-requisitos durante a importação, siga as etapas a seguir.

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, no Painel Ação, na guia **Configurações**, no grupo **Configurações avançadas**, selecione **Parâmetros de usuário**.
3. Defina a opção **Ignorar atualizações de produto e verificação de pré-requisitos de versão durante importação** como **Sim**.

    > [!NOTE]
    > Esse parâmetro é específico do usuário e da empresa.

## <a name="dependencies-on-other-components"></a>Dependências de outros componentes

As configurações de ER podem ser definidas como [dependentes](er-download-configurations-global-repo.md#import-filtered-configurations) de outras configurações. Por exemplo, você pode [importar](er-download-configurations-global-repo.md) uma configuração do [modelo de dados ER](er-overview-components.md#data-model-component) do repositório global para sua instância do [Microsoft Regulatory Configuration Services (RCS)](../../../finance/localizations/rcs-overview.md) ou do Dynamics 365 Finance e criar uma nova configuração [de formato para ER](er-overview-components.md#format-component) que é [derivada](er-quick-start2-customize-report.md#DeriveProvidedFormat) da configuração do modelo de dados ER importada. A configuração do formato ER derivado dependerá da configuração do modelo de dados de base ER.

![Configuração do formato de ER derivado na página "Configurações".](./media/ger-configuration-lifecycle-img1.png)

Quando terminar de criar o formato, você poderá alterar o status da versão inicial da configuração do formato ER de **Rascunho** para **Concluído**. Em seguida, você pode compartilhar a versão concluída da configuração do formato ER [com sua publicação](../../../finance/localizations/rcs-global-repo-upload.md) no repositório global. Em seguida, você pode acessar o repositório global de qualquer instância de nuvem do RCS ou Finance. Em seguida, você pode importar qualquer versão de configuração do ER aplicável ao aplicativo do repositório global para o aplicativo.

![Configuração do formato ER publicado na página do repositório de configuração.](./media/ger-configuration-lifecycle-img2.png)

Com base na dependência de configuração, quando você seleciona a configuração do formato ER no repositório global para importá-la para uma instância do RCS ou Finance recentemente instalada, a configuração do modelo de dados de base ER é automaticamente encontrada no repositório global e importada com a configuração de formato ER selecionada como a configuração básica.

Você também pode exportar sua versão de configuração de formato ER da sua instância RCS ou Finance atual e armazená-la localmente como um arquivo XML.

![Exportação de uma versão da configuração de formato de ER como XML na página "Configurações".](./media/ger-configuration-lifecycle-img3.png)

Nas versões do Finance **antes da versão 10.0.29**, ao tentar importar a versão de configuração do formato ER desse arquivo XML ou de qualquer outro repositório que não seja o repositório global em uma instância do RCS ou Finance recentemente implantada que ainda não tenha nenhuma configuração de ER, a seguinte exceção será lançada para informá-lo de que não é possível obter uma definição básica:

> Referências não resolvidas mantidas<br>
A referência do objeto "\<imported configuration name\>" para o objeto "Base" (\<globally unique identifier of the missed base configuration\>,\<version of the missed base configuration\>) não pode ser estabelecida

![Importar a versão de configuração do formato de ER na página do repositório de configuração.](./media/ger-configuration-lifecycle-img4.gif)

Na versão **10.0.29 e mais recente**, quando você tenta fazer a mesma importação de configuração, se uma configuração básica não puder ser encontrada na instância do aplicativo atual ou no repositório da fonte que você está usando no momento (se aplicável), a estrutura ER tentará automaticamente encontrar o nome da configuração básica ausente no cache do repositório global. Em seguida, ele apresentará o nome e o identificador global exclusivo (GUID) da configuração básica ausente no texto da exceção que é lançada.

> Referências não resolvidas mantidas<br>
A referência do objeto ''\<imported configuration name\>" para o objeto "Base'' (\<name of the missed base configuration\> \<globally unique identifier of the missed base configuration\>,\<version of the missed base configuration\>) não pode ser estabelecida

![Exceção na página do repositório de configuração quando a configuração básica não puder ser encontrada.](./media/ger-configuration-lifecycle-img5.png)

Você pode usar o nome fornecido para encontrar a configuração básica e, depois, importá-la manualmente.

> [!NOTE]
> Essa nova opção só funciona quando pelo menos um usuário já fez login no repositório global usando a página [Repositórios de configuração](er-download-configurations-global-repo.md#open-configurations-repository) ou um dos campos de pesquisa de [repositório](er-extended-format-lookup.md) na instância do Finance atual e quando o conteúdo do repositório global tiver sido armazenado em cache.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de Relatório Eletrônico (ER)](general-electronic-reporting.md)

[Definir a dependência de configurações ER em outros componentes](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

