---
title: SPED ECD
description: Este tópico explica como configurar e gerar arquivos de texto do SPED ECD.
author: ShylaThompson
manager: AnnBe
ms.date: 08/27/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Brazil
ms.author: roschlom
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 3e8d591bbb9ff0ae0a5c81704eb8623dbcf416e8
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3982758"
---
# <a name="sped-ecd"></a>SPED ECD

[!include [banner](../includes/banner.md)]

## <a name="set-up-parameters-for-sped-ecd-text-files"></a>Configurar os parâmetros de arquivos de texto fiscais do SPED ECD

Esta seção explica como especificar a forma como os arquivos de texto fiscais do Sistema Publico de Escrituração Digital (SPED) devem ser salvos antes de você enviá-los às autoridades fiscais federais.

Os arquivos fiscais de texto do SPED contêm informações sobre transações de contabilidade, informações de lucros e perdas, e informações de balanço. As autoridades de imposto federal usam o sistema Contábil de Escrituração Digital (ECD) do SPED para verificar os lucros tributáveis da empresa. 

### <a name="set-up-requirements-for-the-sped-ecd-tax-statement"></a>Configurar requisitos para a declaração de imposto SPED ECD

Para configurar os requisitos para os arquivos de texto fiscais do SPED ECD, siga estas etapas.

1.  Selecione **Livros fiscais** \> **Configuração** \> **Parâmetros das extensões de obrigações fiscais**.
2.  Selecione **SPED ECD** à esquerda e, em seguida, na Guia Rápida **Parâmetros de configuração**, selecione **Abrir**.
3.  Selecione a empresa para a qual gerar o arquivo de texto do SPED ECD.
4.  Selecione o conjunto de dimensões financeiras na qual o formato de arquivo de texto do SPED ECD deve se basear. O conjunto de dimensões financeiras deve incluir a conta principal e as dimensões de centro de custo.
5.  Selecione o local onde o arquivo de texto do SPED ECD deve ser gerado.

    O tipo de registro é atribuído automaticamente com base no tipo da organização fiscal:

    -  **G** – O registro é usado para todas as transações do diário do razão.
    -  **S** – O registro é usado para a empresa SCP.

6.  Selecione o tipo de situação da empresa. As opções a seguir estão disponíveis. Alternativamente, deixe o campo em branco para representar a situação normal.

    -  Divisão
    -  Fusão
    -  Corporação
    -  Fechamento
    -  Transformação

7.  No campo **Período fiscal de abertura**, selecione uma das seguintes opções:

    -  Normal
    -  Abertura
    -  Divisão, Fusão ou Aquisição
    -  Obrigatório

8.  Selecione a versão do formato de arquivo de texto fiscal do SPED ECD a ser gerado.
9.  No campo **Número de inscrição do auditor**, insira o número do auditor da empresa.
10. Insira o nome do auditor.
11. Defina a opção **Empresa de grande porte** como **Sim** se a empresa for de grande porte.

## <a name="generate-and-validate-the-sped-ecd-statement"></a>Gere e valide o demonstrativo ECD SPED 

Esta seção explica como gerar e validar o arquivo de texto para a contabilidade digital (SPED ECD).

Para o demonstrativo SPED ECD, as organizações devem calcular e informar os lucros tributáveis com base nos seguintes tipos de registros da contabilidade:

- Registros de diário e registros de suporte
- Contabilidade e sub-razões
- Balancetes e balanços diários

### <a name="generate-and-validate-a-sped-ecd-text-file"></a>Gerenciar e validar um arquivo de texto SPED ECD

Para gerar e validar o arquivo de texto para o demonstrativo SPED ECD, siga estas etapas.

1.  Selecione **Livros fiscais** \> **Comum** \> **SPED ECD** \> **Gerar o SPED ECD**.
2.  Selecione a organização fiscal para a qual será gerado o arquivo SPED ECD.
3.  Nos campos **Data inicial** e **Data Final** selecione as datas de início e de término das transações do razão incluídas no relatório.
4.  Defina a opção **Incluir demonstrativos contábeis** como **Sim** para gerar o arquivo de texto do Bloco J, além do arquivo SPED ECD.
5.  Selecione o período de cálculo de saldos de demonstrativo financeiro.
6.  Insira o caminho no qual os arquivos devem ser salvos.
7.  No campo **Número do livro**, insira o número do livro contábil.

    O campo **Tipo de escrituração** é definido automaticamente como **G** (Livro Diário completo sem escrituração auxiliar).

8.  Selecione o tipo de situação da empresa. As opções a seguir estão disponíveis. Alternativamente, deixe o campo em branco para representar a situação normal.

    -  Divisão
    -  Fusão
    -  Corporação
    -  Fechamento
    -  Transformação

9.  No campo **Período fiscal de abertura**, selecione uma das seguintes opções:

    -  Normal
    -  Abertura
    -  Divisão, Fusão ou Aquisição
    -  Obrigatório

10. No campo **Versão de layout**, selecione o layout do arquivo SPED ECD.
11. No campo **Tipo de arquivo**, selecione o tipo de arquivo a ser gerado:

    -  Original
    -  Substituto com NIRE
    -  Substituto sem NIRE
    -  Substituto com alterações de NIRE

    O Número de Identificação no Registro de Empresas (NIRE) é inserido na página **Estabelecimento fiscal** na guia rápida **Registro de imposto**.

12. Selecione **OK** para gerar o arquivo SPED ECD.
13. Selecione **Livros fiscais** \> **Comum** \> **SPED ECD** \> **Validar o SPED ECD**.
14. Selecione **OK** para validar o arquivo SPED ECD.

## <a name="additional-resources"></a>Recursos adicionais

[Gerar a obrigação de imposto Sintegra](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/bra-parameters-tax/articles/financials/localizations/latam-bra-set-up-parameters-for-tax-statements.md)
