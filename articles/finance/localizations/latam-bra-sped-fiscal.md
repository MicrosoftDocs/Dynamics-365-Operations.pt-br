---
title: Arquivos fiscais SPED
description: Este artigo explica como configurar e gerar arquivos de exportação SPED para o Brasil.
author: AdamTrukawka
ms.date: 08/27/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: atrukawk
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 526b2e39404ddc63491ada292b7939512601c2be
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278211"
---
# <a name="sped-fiscal-files"></a>Arquivos fiscais SPED 

[!include [banner](../includes/banner.md)]

Os arquivos de texto fiscais do Sistema Público de Escrituração Digital (SPED) contêm informações sobre todas as notas fiscais que foram recebidas e emitidas em um mês para um estabelecimento fiscal específico. As autoridades fiscais federais usam o sistema SPED para verificar os cálculos do Imposto Sobre Circulação de Mercadorias e Serviços (ICMS) e do Imposto sobre Produtos Industrializados (IPI).

## <a name="setup"></a>Configurar

Para poder gerar um arquivo de texto fiscal SPED e enviá-lo às autoridades fiscais federais, você deve especificar os parâmetros que definem como o arquivo de texto fiscal SPED será salvo. Esta seção explica como especificar esses parâmetros na página **Parâmetros do SPED Fiscal**.

1. Selecione **Livros fiscais** \> **Configuração** \> **Parâmetros das extensões de obrigações fiscais**.
2. Selecione **SPED Fiscal** e, em seguida, na Guia Rápida **Parâmetros de configuração**, selecione **Abrir**.
4. Na página **Parâmetros do SPED Fiscal**, selecione o local no qual o arquivo de texto fiscal SPED deve ser salvo.
5. Selecione uma apresentação de perfil. Para a versão atual, apenas a apresentação de perfil **A** tem suporte.
6. Selecione a versão do formato de arquivo de texto fiscal SPED a ser gerado.
7. Selecione o tipo de atividade a ser incluído no arquivo de texto fiscal SPED:

    - **Industrial ou equivalente** – Inclui informações de atividades que estão relacionadas aos setores (por exemplo, a fabricação de mercadorias).
    - **Outros** – Inclui informações para todos os outros tipos de atividades.

8. Defina a opção **Habilitar o bloco K** como **Sim**. Se não habilitar o bloco K, apenas os registros K001 e K999 serão produzidos.
9. Defina a opção **Habilitar ordens de produção** como **Sim**. Esta opção permite gerar os registros K230 e K235 do módulo de manufatura. 

## <a name="generate-the-sped-fiscal-export-file-for-a-month"></a>Gerar o arquivo de exportação fiscal SPED para um mês 

O arquivo de texto fiscal do SPED fornece informações sobre as notas fiscais que foram recebidas e emitidas durante um mês específico. Essas informações são usadas pelas autoridades fiscais. O arquivo de texto fiscal SPED também inclui informações sobre apurações e pagamentos de impostos durante o mês. Esta seção explica como gerar um arquivo de texto fiscal SPED usando a página de listagem **Período de escrituração**.

1. Selecione **Livros fiscais** \> **Comum** \> **Período de escrituração**.
2. Selecione um período de escrituração.
3. No Painel de Ação, na guia **Obrigações fiscais**, selecione **SPED Fiscal**.
4. Especifique o local e o nome do arquivo. O local padrão é especificado na página **Parâmetros do SPED Fiscal** e o nome do arquivo padrão será gerado automaticamente. Na maioria dos casos, você deve aceitar o nome do arquivo padrão.
5. No campo **Tipo de arquivo**, selecione **Original** ou **Substituto**.
6. Selecione a versão. A versão padrão é especificada na página **Parâmetros do SPED Fiscal** .
7. Defina a opção **Habilitar o bloco K** como **Sim**. A definição padrão é especificada na página **Parâmetros do SPED Fiscal** .
8. Opcional: Na Guia Rápida **Executar em segundo plano**, especifique as opções para o processamento em lotes. Você pode usar o processamento em lote se o arquivo tiver de ser gerado posteriormente ou em um servidor, e não no computador.
9. Selecione **OK**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
