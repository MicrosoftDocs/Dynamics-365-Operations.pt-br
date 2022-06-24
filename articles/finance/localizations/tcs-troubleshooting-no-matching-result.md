---
title: Nenhum resultado correspondente encontrado
description: Este artigo explica como solucionar o erro "Não foi possível encontrar nenhum resultado correspondente" no serviço Cálculo de Imposto.
author: hangwan
ms.date: 03/25/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: hangwan
ms.search.validFrom: 03/23/2022
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: d3bbc76741fdd018d1b2987538b8de7f6d92ee53
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845134"
---
# <a name="no-matching-result-could-be-found"></a>Nenhum resultado correspondente encontrado

[!include [banner](../includes/banner.md)]

Este artigo explica as etapas de solução de problemas que podem ser executadas se você receber um erro "Não foi possível encontrar nenhum resultado correspondente" no serviço Cálculo de Imposto.

## <a name="symptom"></a>Sintoma

Você recebe a seguinte mensagem de erro: "Cabeçalho/Linhas - 1, Grupo de impostos, não foi possível encontrar nenhum resultado correspondente".

```json
======================Tax service calculation result JSON:===========================
{
    "taxDocument": {
        "Header": [
            {
                "Lines": [
                    {
                        ...
                        "Errors": [
                            {
                                "Code": "TaxSetup20000",
                                "Message": "Header/Lines - 1, Tax group applicability, no matching result could be found."
                            }
                        ],
                        "Adjustment": null
                    }
                ],
                "Measures": {
                    ...
                },
                ...
            }
        ]
    },
    ...
}
```

## <a name="cause"></a>Causa

O problema ocorre quando a configuração do recurso no Regulatory Configuration Service (RCS) está incorreta.

## <a name="troubleshoot"></a>Solucionar problemas

1. Baixe o arquivo de solução de problemas. Para obter mais informações, consulte [Habilitar o modo de depuração para a solução de problemas](tcs-troubleshooting-enable-debug-mode.md).
2. Compare a entrada do cálculo do Serviço de imposto com a configuração do recurso para corrigir o problema de configuração.

    O exemplo a seguir mostra a entrada de cálculo do Serviço de imposto.

    ```json
    ===============================Tax service calculation input JSON:=====================================
    {
        "TaxableDocument": {
            "Header": [
                {
                    "Lines": [
                        {
                            ...
                        }
                    ],
                    "Business Process": "Sales",
                    "Ship From Zip Code": "30159",
                }
            ]
        },
        "Parameter": {
            ...
        },
        "Adjustment": {
            "Lines": {}
        }
    }
    ```

    A tabela a seguir lista a aplicabilidade do grupo de impostos no RCS.

    | Cabeçalho.Processo empresarial | Linhas.Unidade de Negócios | Cabeçalho.Remeter do CEP | Grupo de Impostos |
    |-------------------------|---------------------|---------------------------|-----------|
    | Diário                 |                     |                           | Grupo A   |
    | Vendas                   |                     | 30160                     | Grupo B   |

    De acordo com a entrada do cálculo do Serviço de imposto, o valor de **Processo empresarial** no cabeçalho é **Vendas** e o valor de **Remeter do CEP** no cabeçalho é **30159**. Essa entrada se baseia na configuração de regras de aplicabilidade no RCS. Como não há linha correspondente, ocorre o erro.

    > [!NOTE]
    > Se o valor na regra de aplicabilidade estiver em branco, a regra será aplicável a qualquer valor.

## <a name="mitigation"></a>Redução

Siga estas etapas para corrigir o erro:

1. No RCS, acesse **Recursos de globalização** \> **Cálculo de imposto**.
2. Crie uma versão do recurso.
3. Adicione uma linha para as informações correspondentes.

    | Cabeçalho.Processo empresarial | Linhas.Unidade de Negócios | Cabeçalho.Remeter do CEP| Grupo de Impostos |
    |-------------------------|---------------------|--------------------------|-----------|
    | Diário                 |                     |                          | Grupo A   |
    | Vendas                   |                     | 30160                    | Grupo B   |
    | Vendas                   |                     | 30159                    | Grupo B   |

4. Publique a versão da configuração do recurso.
5. No Microsoft Dynamics 365 Finance, acesse **Imposto** \> **Configuração** \> **Configuração do imposto** \> **Parâmetros de cálculo do imposto** e selecione a nova versão.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
