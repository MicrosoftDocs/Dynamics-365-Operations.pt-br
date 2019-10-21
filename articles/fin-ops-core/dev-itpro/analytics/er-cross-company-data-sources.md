---
title: Fontes de dados interempresariais no relatório eletrônico (ER)
description: Este tópico explica como você pode usar fontes de dados interempresariais no relatório eletrônico (ER).
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: dc98f060bbb27958436cd2183bb469f821d04320
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181487"
---
# <a name="cross-company-data-sources-in-electronic-reporting-er"></a>Fontes de dados interempresariais no relatório eletrônico (ER)

[!include[banner](../includes/banner.md)]

Você pode criar os formatos de relatórios eletrônicos (ER) para gerar documentos de saída em vários formatos. Quando um documento é gerado, um formato de ER chama as fontes de dados que foram configuradas em um mapeamento de modelo de ER correspondente. Para configurar o acesso a tabelas de aplicativo para a recuperação do registro, você pode usar fontes de dados de ER do tipo **Registros de tabela** . Quando a tabela de acesso é uma tabela compartilhada (isto é, uma tabela na qual os dados são salvos sem um identificador da empresa), esta fonte de dados retorna todos os registros. Quando a tabela de acesso é uma tabela dependente da empresa (isto é uma tabela onde os dados são salvos por empresa), esta fonte de dados retorna somente os registros que foram salvos para a empresa atual (isto é, o contexto da empresa que o formato de ER está executando).

Cada fonte de dados do tipo **Registros de tabela** em um mapeamento de modelo pode agora ser marcado como uma fonte de dados interempresariais. No entanto, você pode usar as fontes de dados do tipo **Registros da tabela** para acessar os dados interempresariais nas tabelas do aplicativo.

Se você marcar uma fonte de dados como interempresarial, ocorre o seguinte comportamento:

- Para uma fonte de dados que se refere a qualquer tabela compartilhada, exceto CompanyInfo, a fonte de dados retorna todos os registros que existem na tabela referenciada. 
- Para uma fonte de dados que se refere a tabela de CompanyInfo, mesmo que CompanyInfo seja uma tabela compartilhada, a fonte de dados retorna registros que contêm o identificador de uma empresa do escopo definido.
- Para qualquer tabela dependente da empresa, a fonte de dados retorna os registros da tabela referenciada que contêm o identificador de uma empresa do escopo definido.

Na caixa de diálogo de consulta do sistema, quando a opção **Solicitar consulta** for ativada para qualquer fonte de dados que for marcada como interempresarial, você pode selecionar manualmente uma ou mais empresas para incluir na guia **Intervalo da empresa**.

> [!IMPORTANT]
> Como outros filtros, o filtro da empresa é persistente como o último valor usado para consultas quando você executa um formato de ER. O filtro não é alterado automaticamente se você alterar o valor interempresarial de uma fonte de dados. Para usar um valor diferente interempresarial para outra fonte de dados, exclua a seleção específica do usuário correspondente.

Para cada fonte de dados que é marcada como interempresarial, selecione os registros que você deseja, usando as funções **FILTER** e **WHERE** nas expressões do ER. O campo **dataAreaID** também pode ser usado como identificador da empresa. Atualmente, o campo **dataAreaID** está limitado aos seguintes tipos de condições, quando a função **FILTER** for usada:

- Somente condições que têm uma única comparação do campo **dataAreaID** são suportadas.
- Apenas as comparações com as expressões que não depende dos itens de lista de registros são permitidas.

No entanto, a seguinte expressão é válida.

```
FILTER (MyTable, MyTable.dataAreaID = $StringUserInputParameter)
While shown below expressions will not pass the validation:
FILTER (MyTable, MyTable.dataAreaID = MyTable2RecordsList.MyField)
FILTER (MyTable, 
    OR(
        MyTable.dataAreaID = $StringUserInputParameter1,
        MyTable.dataAreaID = $StringUserInputParameter2
    )
)
```

Por padrão, o escopo inclui todas as empresas do aplicativo atual. Porém, poderá ser restrito. Para restringir o escopo de acesso a dados interempresarial para um único formato de ER, atribua uma hierarquia organizacional específica ao formato. Quando a hierarquia é definida para um formato de ER, apenas os registros das entidades legais que são apresentados na hierarquia atribuída são retornados, mesmo que o formato chame fontes de dados interempresariais. Quando uma referência a uma hierarquia que não existe é definida para um formato de ER, o escopo padrão será aplicado e o formato chama as fontes de dados interempresariais. Nessa situação, os registros de todas as empresas do aplicativo são retornadas.

Observe que quando a opção **Usar o rascunho** está ativada para aquela atribuída a uma hierarquia de organização do formato de ER único, as entidades legais da versão rascunho desta hierarquia serão usadas para identificar o escopo das fontes de dados interempresariais. Se a versão de rascunho não existir, as entidades legais da última versão publicada dessa hierarquia da organização serão usadas para isso.

Observe que quando a opção **Usar rascunho** estiver desativada para aquela atribuída a uma hierarquia de organização do formato de ER único, as entidades legais da última versão publicada desta hierarquia da organização serão usadas para identificar o escopo das fontes de dados interempresariais. A eficiência de data das hierarquias de organização não é suportada ainda na estrutura de ER.

A hierarquia pode ser atribuída a um formato em uma página específica que pode ser acessada do espaço de trabalho de ER ou usando o item de menu **Administração da organização \> Relatório eletrônico \> Filtro de entidade legal para formatos**. Para acessar a página, o privilégio **Manter filtros de entidade legal para formatos** (ERMaintainFormatMappingLegalEntityFilters) deve ser concedido a um usuário. A restrição do escopo de entidades legais baseadas para o formato é aplicada, além das restrições que o usuário pode especificar manualmente na caixa de diálogo de consulta do sistema. A interseção dessas restrições é usada quando o formato é executado.

Para saber mais sobre este recurso, execute a guia de tarefas **ER Acessar registro de tabelas dependentes da empresa no modo interempresarial**, que faz parte do processo de negócios 7.5.4.3 Adquirir/Desenvolver componentes de serviço/solução de TI (10677) e pode ser baixada do [Centro de Download Microsoft](https://go.microsoft.com/fwlink/?linkid=874684). Este guia de tarefas o orienta por todo o processo de configuração de um mapeamento de modelos de ER e formato de ER para acessar tabelas do aplicativo no modo interempresarial.

Baixe os seguintes arquivos para completar o guia de tarefas:

- [Configuração de modelo ER - CrossCompanyDataAccessModel.xml](https://go.microsoft.com/fwlink/?linkid=874111)
- [Configuração de formato ER - CrossCompanyDataAccessFormat.xml](https://go.microsoft.com/fwlink/?linkid=874111)
