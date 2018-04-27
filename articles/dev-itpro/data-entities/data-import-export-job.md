---
title: "Trabalhos de importação e exportação de dados"
description: "Use o espaço de trabalho de gerenciamento de dados para criar e gerenciar trabalhos de importação e de exportação de dados."
author: Sunil-Garg
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application user
ms.reviewer: margoc
ms.search.scope: Operations
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: fc47f6cd9cfe4a850e0959bf89da086ca82f3b69
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="data-import-and-export-jobs"></a>Trabalhos de importação e exportação de dados

[!INCLUDE [banner](../includes/banner.md)]

Para criar e gerenciar trabalhos de importação e de exportação de dados no Microsoft Dynamics 365 for Finance and Operations use o espaço de trabalho **Gerenciamento de dados**. Por padrão, o processo de importação e exportação criar uma tabela de preparo para cada entidade no banco de dados de destino. As tabelas de preparo permitem verificar, limpar ou converter dados antes de movê-los.

> [!NOTE]
> Este tópico pressupõe que você está familiarizado com as [entidades de dados](data-entities.md).

## <a name="data-importexport-process"></a>Processo de importação/exportação de dados
Seguem as etapas para importar ou exportar dados.

1. Criar um trabalho de importação ou de exportação onde você conclua as seguintes tarefas:

    - Definir a categoria do projeto.
    - Identificar as entidades a serem importadas ou exportadas.
    - Definir o formato de dados para o trabalho.
    - Definir as sequências de entidades, de modo que sejam processadas em grupos lógicos e uma ordem que faça sentido.
    - Determinar se usa tabelas de preparo.

2. Validar se os dados dos dados de origem e de destino estão mapeados corretamente.
3. Verificar a segurança para seu trabalho de importação ou de exportação.
4. Executar o trabalho de importação ou de exportação.
5. Validar se o trabalho foi executado conforme esperado, examinando o histórico de trabalho.
6. Limpar as tabelas de preparo.

As seções restantes deste tópico fornecem mais detalhes sobre cada etapa do processo.

> [!NOTE]
> Para atualizar o Formulário de exportação/importação de dados para ver o progresso mais recente, use o ícone de atualização do formulário. A atualização do navegador não é recomendada porque interromperá qualquer trabalho de exportação/importação que não for executado em lotes.

## <a name="create-an-import-or-export-job"></a>Criar um trabalho de importação ou de exportação
Um trabalho de importação ou exportação de dados pode ser executado uma ou várias vezes.

### <a name="define-the-project-category"></a>Definir a categoria do projeto
Recomenda-se que você aproveite o tempo para selecionar uma categoria de projeto adequado para o trabalho de importação ou de exportação. As categorias de projeto podem ajudá-lo a gerenciar trabalhos relacionados.

### <a name="identify-the-entities-to-import-or-export"></a>Identificar as entidades a serem importadas ou exportadas
Você pode adicionar entidades específicas a um trabalho de importação ou de exportação ou selecionar um modelo a ser aplicado. Os modelos preenchem um trabalho com uma lista das entidades. A opção **Aplicar modelo** está disponível depois que você fornecer um nome ao trabalho e salvar o trabalho.

### <a name="set-the-data-format-for-the-job"></a>Definir o formato de dados para o trabalho
Quando você seleciona uma entidade, é necessário selecionar o formato de dados que será exportado ou importado. Você define formatos usando o bloco **Configuração das fontes de dados** . Um formato de dados de origem é uma combinação de **Tipo**, **Formato de arquivo**, **Delimitador de linha** e **Delimitador de colunas**. Há outros atributos também, mas esses são os principais a serem compreendidos A tabela a seguir lista as combinações válidas.

| **Formato de Arquivo**        | **Delimitador de linha/coluna**                   | **Estilo XML**             |
|------------------------|--------------------------------------------|---------------------------|
| Excel                  | Excel                                      | \-NA-                     |
| XML                    | \-NA-                                      | Elemento XML Atributo XML |
| Delimitado, largura fixa | Vírgula, ponto e vírgula, guia, barra vertical, dois pontos | \-NA-                     |



### <a name="sequence-the-entities"></a>Definir sequências das entidades
As entidades podem ser sequenciadas em um modelo de dados, ou em trabalhos de importação e exportação. Quando você executa um trabalho que contém mais de uma entidade de dados, você deve garantir que as entidades de dados estão sequenciadas corretamente. Você define a sequência, de forma que possa tratar todas as dependências funcionais entre entidades. Se as entidades se não tiverem dependências funcionais, elas podem ser programadas para importação ou exportação paralela.

#### <a name="execution-units-levels-and-sequences"></a>Unidades de execução, níveis, e sequências
A unidade de execução, nível na unidade de execução e sequência de ajuda da entidade controlam a ordem em que os dados são exportados ou importados.

- As entidades em unidades diferentes de execução são processados em paralelo.
- Em cada unidade de execução, as entidades são processadas em paralelo, se tiverem o mesmo nível.
- Em cada nível, as entidades são processadas de acordo com o número de sequência daquele nível.
- Depois que um nível for processado, o nível seguinte será processado.

#### <a name="resequencing"></a>Novo sequenciamento
Convém sequenciar novamente as entidades nas seguintes situações:

- Se apenas um trabalho de dados for usado para todas as suas alterações, é possível usar as opções de novo sequenciamento para otimizar o tempo de execução do trabalho completo. Nesses casos, você pode usar a unidade de execução para representar o módulo, o nível para representar a área de recurso no módulo e a sequência para representar a entidade. Usando esta abordagem, você pode trabalhar nos módulos em paralelo, mas pode ainda trabalhar em sequência em um módulo. Para ajudar a garantir que as operações paralelas são bem-sucedidas, considere todas as dependências.
- Se vários trabalhos de dados forem usados (por exemplo, um trabalho para cada módulo), você pode usar o sequenciamento para afetar o nível e a sequência de entidades para a execução ideal.
- Se não houver nenhuma dependência, é possível sequenciar as entidades em unidades de execução diferentes para a otimização máxima.

O menu **Nova sequência** fica disponível quando várias entidades forem selecionadas. Você pode efetuar novo sequenciamento com base na unidade de execução ou nas opções de sequência. Você pode definir um incremento para sequenciar novamente as entidades que foram selecionadas. A unidade, o nível, e/ou o número de sequência selecionados para cada entidade são atualizados por incremento especificado.

#### <a name="sorting"></a>Classificação
Você pode usar a opção **Classificar por** para exibir a lista de entidades na ordem sequencial.

## <a name="validate-that-the-source-data-and-target-data-are-mapped-correctly"></a>Valide se os dados dos dados de origem e de destino estão mapeados corretamente
Mapeamento é uma função que se aplica aos trabalhos de importação e exportação.

- No contexto de um trabalho de importação, o mapeamento descreve quais colunas no arquivo de origem se tornam as colunas na tabela de preparo. Portanto, o sistema pode determinar quais dados da coluna no arquivo de origem devem ser copiados para a coluna da tabela de preparo.
- No contexto de um trabalho de exportação, o mapeamento descreve quais colunas da tabela de preparo (isto é, da origem) se tornam as colunas no arquivo de destino.

Se os nomes de colunas na tabela de preparo e o arquivo forem correspondentes, o sistema estabelecerá automaticamente o mapeamento, com base nos nomes. Entretanto, se os nomes forem diferentes, as colunas não serão mapeadas automaticamente. Nesses casos, você deverá concluir o mapeamento, selecionando a opção **Exibir mapa** na entidade, no trabalho de dados.

Há duas exibições de mapeamento: **Visualização de mapeamento**, que é a exibição padrão, e **Detalhes de mapeamento**. Um asterisco vermelho (\*) identifica os campos obrigatórios na entidade. Esses campos devem ser mapeados antes de você trabalhar com a entidade. Você pode desmapear outros campos, conforme necessário, quando trabalhar com a entidade. Para desmapear um campo, selecione-o na coluna **Entidade** ou na coluna **Origem** e, em seguida, marque a opção **Excluir seleção**. Selecione **Salvar** para salvar suas alterações, e feche a página para retornar ao projeto. Você pode usar o mesmo processo para editar o mapeamento do campo da origem para o preparo, após a importação.

Você pode gerar um mapeamento na página, selecionando **Gerar mapeamento de origem**. Um mapeamento gerado atua como um mapeamento automático. Portanto, você deve mapear manualmente todos os campos não mapeados.

![Mapeamento de dados](./media/dixf-map.png)

## <a name="verify-the-security-for-your-import-or-export-job"></a>Verificar a segurança para seu trabalho de importação ou de exportação
O acesso ao espaço de trabalho **Gerenciamento de dados** pode ser restrito, de forma que os usuários não administradores possam acessar somente os trabalhos de dados específicos. O acesso a um trabalho de dados implica em acesso completo ao histórico da execução desse trabalho e acesso a tabelas de preparo. Portanto, você deve garantir que os controles de acesso apropriados estão em vigor, ao criar um trabalho de dados.

### <a name="secure-a-job-by-roles-and-users"></a>Proteger um trabalho por funções e usuário
Use o menu **Funções aplicáveis** para limitar o trabalho a uma ou mais funções de segurança. Somente os usuários dessas funções terão acesso ao trabalho.

Também é possível restringir um trabalho a usuários específicos. Quando você proteger um trabalho por usuários, em vez de por funções, há mais controle se vários usuários forem atribuídos a uma função.

### <a name="secure-a-job-by-legal-entity"></a>Proteger um trabalho por entidade legal
Os trabalhos de dados são globais por natureza. Portanto, se um trabalho de dados foi criado e usado em uma entidade legal, ele ficará visível em outras entidades legais no sistema. Esse comportamento padrão pode ser preferencial em alguns cenários de aplicativo. Por exemplo, uma organização que importa notas fiscais usando entidades de dados pode fornecer uma equipe de processamento centralizado de nota fiscal que é responsável por gerenciar erros de faturamento para todas as divisões da organização. Neste cenário, é útil para a equipe de processamento centralizado de faturamento ter acesso aos trabalhos de importação de nota fiscal das entidades legais. Portanto, o comportamento padrão atende ao requisito de uma perspectiva da entidade legal.

Entretanto, uma organização pode optar por ter equipes de processamento de nota fiscal por entidade legal. Nesse caso, uma equipe em uma entidade legal deve ter acesso apenas a trabalhos de importação de faturamento em sua própria entidade legal. Para atender a este requisito, você pode configurar o controle de acesso baseado na entidade legal em trabalhos de dados usando o menu **Entidades legais aplicáveis** no trabalho de dados. Depois que a configuração for feita, os usuários podem ver somente trabalhos que estão disponíveis na entidade legal na qual eles estão conectados atualmente. Para consultar trabalhos de outra entidade legal, os usuários devem alternar para essa entidade legal.

Um trabalho pode ser protegido por funções, usuários e por entidade legal simultaneamente.

## <a name="run-the-import-or-export-job"></a>Executar o trabalho de importação ou de exportação
Você pode executar um trabalho uma vez, selecionando o botão **Importar** ou **Exportar** após definir o trabalho. Para configurar um trabalho recorrente, selecione **Criar trabalho de dados recorrente**.

## <a name="validate-that-the-job-ran-as-expected"></a>Validar se o trabalho foi executado conforme esperado
O histórico de trabalho está disponível para solução de problemas e investigação sobre trabalhos de importação e exportação. As execuções do histórico do trabalho são organizadas por intervalos de tempo.

![Intervalos do histórico de trabalho](./media/dixf-job-history.md.png)

Cada execução de trabalho fornece os seguintes detalhes:

- Detalhes da execução
- Log de execução

Os detalhes de execução mostram o estado de cada entidade de trabalho que trabalho processou. Portanto, você pode localizar rapidamente as seguintes informações:

- As entidades que foram processadas
- Para uma pessoa, quantos registros foram processados com êxito, e quantos com falha
- Os registros de preparo de cada entidade

Podem baixar os dados de preparo em um arquivo para exportação de trabalho, ou pode baixá-los como um pacote para trabalhos de importação e exportação.

A partir dos detalhes de execução, você também pode abrir este log de execução.

## <a name="clean-up-the-staging-tables"></a>Limpar as tabelas de preparo
Você pode limpar as tabelas de preparo usando o recurso **Limpeza de preparo** no espaço trabalho **Gerenciamento de dados**. Você pode usar as opções para selecionar os registros que devem ser excluídos da tabela de preparo:

- **Entidade** – Se apenas uma entidade for fornecida, todos os registros dessa tabela de preparo da entidade serão excluídos. Selecione esta opção para limpar todos os dados da entidade em todos os projetos de dados e de todos os trabalhos.
- **ID de trabalho** – Se somente um ID de trabalho for fornecido, todos os registros de todas as entidades no trabalho selecionado serão excluídos das tabelas de preparo apropriadas.
- **Projetos de dados** – Se apenas um projeto de dados for selecionado, todos os registros de todas as entidades e em todos os trabalhos do projeto de dados selecionado serão excluídos.

Você também pode combinar as opções para restringir mais o conjunto de registros que foi excluído.

