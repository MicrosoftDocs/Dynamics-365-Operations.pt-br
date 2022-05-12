---
title: Não é possível determinar o código de imposto
description: Este tópico explica como solucionar problemas de erro "Não é possível determinar o código de imposto" do serviço Cálculo de Imposto.
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
ms.openlocfilehash: 3c0914f0013ad2de61cd5a59e3092fef149742e4
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645374"
---
# <a name="tax-code-cannot-be-determined"></a>Não é possível determinar o código de imposto

[!include [banner](../includes/banner.md)]

Este tópico explica as etapas de solução de problemas que podem ser executadas se você receber um erro "Não é possível determinar o código de imposto" no serviço Cálculo de Imposto.

## <a name="symptom"></a>Sintoma

Você recebe a seguinte mensagem de erro: "Cabeçalho/Linhas –1, não é possível determinar o código de imposto". Como alternativa, você encontrará o erro no arquivo de solução de problemas, conforme mostrado no exemplo a seguir. Para obter mais informações, consulte [Habilitar o modo de depuração para a solução de problemas](tcs-troubleshooting-enable-debug-mode.md).

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
                                "Code": "TaxSetup20001",
                                "Message": "Header/Lines - 1, tax code cannot be determined."
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

O problema provavelmente ocorre porque o grupo de impostos e o grupo de impostos do item não fazem interseção.

## <a name="troubleshoot"></a>Solucionar problemas

Siga estas etapas para solucionar o problema.

1. No arquivo de solução de problemas, verifique se o grupo de impostos e o grupo de impostos do item foram determinados. Se os valores para **Grupo de Impostos** e **Grupo de Impostos do Item** estiverem em branco, o grupo de impostos e o grupo de impostos do item não foram determinados. Se eles tiverem sido determinados, os resultados podem estar incorretos.

    Veja aqui um exemplo de um arquivo de solução de problemas.

    ```json
    ======================Tax service calculation result JSON:===========================
    {
        "taxDocument": {
            "Header": [
                {
                    "Lines": [
                        {
                            "Tax Codes": {},
                            "Measures": {
                                "Tax Group": "Group A",
                                "Item Tax Group": "Group B"
                            },
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

2. Verifique se a opção **Substituir imposto** na guia **Configuração** dos detalhes da linha da ordem de venda está habilitada.

    - Se estiver habilitada, os códigos de imposto serão determinados pelos valores de **Grupo de impostos** e **Grupo de impostos do item** inseridos na linha da transação. Verifique se esses valores foram inseridos corretamente.
    - Se ela não estiver habilitada, verifique se os valores corretos foram definidos para os campos **Aplicabilidade do grupo de impostos** e **Aplicabilidade do grupo de impostos do item**. Para obter mais informações, consulte [Não foi possível encontrar nenhum resultado correspondente](tcs-troubleshooting-no-matching-result.md).

3. Se o grupo de impostos e o grupo de impostos do item foram determinados corretamente, determine se há interseções para eles.

    1. No RCS, acesse **Recursos de imposto** \> **Códigos e grupos de impostos** \> **Grupo de impostos**.

        | Linha.Grupo de Impostos | Códigos de imposto |
        |----------------|-----------|
        | Grupo A        | A         |

    2. Acesse **Recursos de imposto** \> **Códigos e grupos de impostos** \> **Grupo de impostos do item**.

        | Linha.Grupo de Impostos do Item | Códigos de imposto |
        |---------------------|-----------|
        | Grupo B             | E         |

    Se não houver interseção para o grupo de impostos e o grupo de impostos do item, o código de imposto não será determinado.

## <a name="mitigation"></a>Redução

1. Siga cada etapa na seção [Solução de problemas](#troubleshoot) deste tópico e corrija a configuração conforme necessário. Se o grupo de impostos e o grupo de impostos do item não tiverem sido determinados corretamente, consulte [Não foi possível encontrar nenhum resultado correspondente](tcs-troubleshooting-no-matching-result.md).
2. Se não houver interseção para o grupo de impostos e o grupo de impostos do item, crie uma nova versão do recurso no RCS e corrija a configuração.

    - Acesse **Recursos de imposto** \> **Códigos e grupos de impostos** > **Grupo de impostos do item**.

        | Linha.Grupo de Impostos do Item | Códigos de imposto |
        |---------------------|-----------|
        | Grupo B             | A;B       |

    O código de imposto será determinado como **A**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
