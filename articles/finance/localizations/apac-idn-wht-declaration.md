---
title: Relatório de imposto retido na fonte para a Indonésia
description: Este artigo explica como configurar e gerar o relatório de imposto retido na fonte para a Indonésia.
author: sndray
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: ''
ms.search.region: Global
ms.author: sndray
ms.search.validFrom: 2021-12-02
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 8acd9442ff4f0b7c19e3b4fcf211acce002e43d5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883171"
---
# <a name="withholding-tax-report-for-indonesia-id-00005"></a>Relatório de imposto retido na fonte para a Indonésia (ID-00005)

[!include [banner](../includes/banner.md)]

Este artigo explica como configurar e gerar o arquivo de retenção de imposto de PPH que as entidades legais na Indonésia usam para relatar transações de retenção no aplicativo e-Bupot.

A DGT (autoridade de imposto da Indonésia) determina que os empresários tributáveis (PKP) registrados no artigo 23 e/ou o artigo 26 do KPP Pratama como retenções de imposto/coletores de imposto de renda (PPh) devem relatar eletronicamente o artigo 23 e 26 de restituição de imposto de renda usando o aplicativo e-Bupot. 

- **Artigo 23** – O relatório inclui todas as transações de retenção de fornecedores nas quais o código de país/região do endereço principal é o código da Indonésia.
- **Artigo 26** – O relatório inclui todas as transações de retenção de fornecedores nas quais o código de país/região do endereço principal não é o código da Indonésia.

## <a name="prerequisites"></a>Pré-requisitos

- O público-alvo principal da entidade legal deve estar na Indonésia.
- No espaço de trabalho **Gerenciamento de recursos**, o recurso **Demonstrativo de benefícios** deve estar habilitado. Para obter mais informações sobre como habilitar recursos, consulte [Visão geral do gerenciamento de recursos.](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)

### <a name="download-electronic-reporting-configurations"></a>Baixar configurações de Relatório eletrônico

A geração de um arquivo de importação é baseada em configurações de Relatório eletrônico (ER). Para obter mais informações sobre os recursos e conceitos de relatórios configuráveis, consulte [Relatórios eletrônicos](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

Para ambientes de produção e de teste de aceitação de usuários (UAT), siga as instruções em [Baixar configurações de Relatório eletrônico do Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

Para gerar o arquivo de importação, carregue as seguintes configurações do repositório:

- **Declaração de imposto modelo.versão.93.xml** ou uma versão posterior
- **Modelo de declaração de imposto mapeamento.versão.93.153.xml** ou uma versão posterior
- **Importação do esquema WHT PPh (ID).versão.93.14** ou uma versão posterior

## <a name="set-up-general-ledger-parameters"></a>Configurar parâmetros de Contabilidade

1. Vá para **Imposto** \> **Configuração** \> **Parâmetros de contabilidade**.
2. Na guia **Imposto retido na fonte**, no campo **Mapeamento de formato de declaração WHT**, selecione **Importação do esquema WHT PPh (ID)**. 
3. Vá para **Imposto** \> **Configuração** \> **Imposto retido na fonte** \> **Tipos de receita de imposto retido na fonte** para configurar o tipo de receita de imposto retido na fonte **Kode Bukti Potong** e atribua os códigos aos grupos de imposto retido na fonte do item relacionado. Os códigos são necessários para gerar o arquivo de integração usando o aplicativo e-Bupot. 

## <a name="generate-the-withholding-import-file"></a>Gerar o arquivo de importação de retenção

O processo de preparação e de geração do arquivo do e-Bupot para um período específico é baseado nas transações de retenção de imposto lançadas durante a liquidação ou lançar o trabalho de imposto de pagamento.

Siga estas etapas para gerar o arquivo.

1. Vá para **Imposto** \> **Declarações** \> **Retenção de imposto** \> **Arquivo de importação PPH e-bupot 23 e 26**.
2. Selecione a data de início e término para o relatório e selecione o período da liquidação.
3. Insira a data de transação e selecione **OK**.
4. Selecione o idioma. Todos os relatórios são traduzidos para inglês dos EUA (**en-us**) e indonésio (**id**).
5. Selecione o tipo comercial e insira os números de cheque e documento. 
6. Verifique se o relatório foi assinado pelo gerente. Essas informações estão relatadas no arquivo. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
