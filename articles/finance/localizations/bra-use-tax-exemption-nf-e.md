---
title: NT2019.001 – Regras de benefícios e isenções fiscais para NF-e/NFC-e
description: Este tópico fornece informações sobre as vantagens e isenções de imposto ICMS em notas fiscais para o Brasil.
author: gionoder
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Brazil
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 309ad74a5fa00ca94d4edab54eb98338044eb6b3fc61d8a86dae5a5dea720351
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751240"
---
# <a name="nt2019001---tax-benefits-and-exemptions-rules-for-nf-enfc-e"></a>NT2019.001 – Regras de benefícios e isenções fiscais para NF-e/NFC-e

[!include [banner](../includes/banner.md)]

Nota técnica de NF-e NT 2019.001 exige que a descrição de benefícios e isenções de imposto ICMS seja imposta de forma mais precisa quando os modelos de documento fiscal 55 (NF-e) e 65 (NFC-e) são emitidos.

Regras de validação específicas foram introduzidas nos serviços de recepção dos serviços Web da NF-e/NFC-e. Essas regras verificam a compatibilidade entre o uso de códigos de benefício associados ao benefício ou à isenção do imposto ICMS e o código de tributação (CST) inserido no XML. A verificação é concluída quando a autorização de NF-e/NFC-e é solicitada.

No entanto, as especificações da nota técnica deixam a vontade do estado para adotar as regras de validação e determinar as próprias regras de compatibilidade entre o código de benefício e o CST. O estado também determina as regras de exceção quando a verificação de compatibilidade entre o código de benefício e o CST deve ser ignorada pelos serviços de recepção dos serviços Web.

Para obter mais informações sobre as regras e exceções de compatibilidade, consulte a versão mais recente da observação técnica NT 2019.001 no [portal da NF-e](http://www.nfe.fazenda.gov.br/portal/principal.aspx). Para obter mais informações sobre as regras de validação, consulte as regras N12-85, N12-86, N12-90, N12-94, N12-97 e N12-98 na mesma nota técnica. No [portal da NF-e](http://www.nfe.fazenda.gov.br/portal/principal.aspx), você também pode exibir a documentação adicional "TABELA\_cBenef \_X\_CST" (a **tabela cBenef x CST**), que descreve o relacionamento válido entre o código de benefício e o CST para cada estado.

Nota técnica NT 2019.001 também inclui informações detalhadas sobre a adoção das regras por cada estado.

> [!NOTE]
> O conceito, a configuração e o uso de benefícios e isenções de imposto no contexto da localização brasileira não estão no escopo deste tópico. Para obter mais informações, consulte a [visão geral de impostos do Brasil](latam-bra-calculate-taxes.md).

## <a name="feature-overview"></a>Visão geral do recurso

Por meio deste recurso, os usuários executarão as seguintes tarefas:

- Adicione **\<vICMSDeson\>** e **\<motDesICMS\>** ao XML que é gerado a partir de cenários em que NF-e/NFC-e são emitidas.
- Configure o código de benefício para as vantagens e isenções de imposto ICMS, de acordo com a tabela **cBenef x CST**.
- Insira o código de benefício na marca **\<cBenef\>**, de acordo com a tabela **cBenef x CST**.
- Valide a compatibilidade entre o código de benefício e o CST, de acordo com as regras de validação das notas técnicas NT 2019.001 e a tabela **cBenef x CST**.

## <a name="turn-on-the-technical-note-feature"></a>Ative o recurso da nota técnica

> [!NOTE]
> Essas informações só se aplicam ao Microsoft Dynamics 365 Finance e ao Dynamics 365 Supply Chain Management.

1. Acesse **Administração da organização \> Organizações \> Estabelecimentos fiscais \> Estabelecimentos fiscais**.
2. Selecione o estabelecimento fiscal.
3. Na FastTab **NF-e e NFC-e federal**, selecione **Editar**.
4. Na seção **Notas técnicas da NF-e**, defina a opção **Habilitar nota técnica de NF-e** como **Sim**.
5. No campo **Notas técnicas da NF-e**, selecione **Nota técnica 2019.001 v 1,40**.
6. Selecione **Salvar**.

> [!IMPORTANT]
> Depois que você selecionar uma versão posterior à **Nota técnica 2019.001 v 1,10** no campo **Notas técnicas da NF-e**, a página **Tipos de códigos de benefícios** (**Imposto \> Configuração \> Imposto de vendas \> Tipos de códigos de benefícios**) se tornará obsoleta e não será mais usada.

## <a name="add-exempt-tags-and-validate-benefit-codes-parameters"></a>Adicionar marcas isentas e validar parâmetros de códigos de benefício

O novos parâmetros a seguir foram introduzidos:

- **Adicionar marcas isentas** – quando esse parâmetro é ativado, as marcas **\<vICMSDeson\>** e **\<motDesICMS\>** são adicionadas ao XML quando a NF-e/NFC-e é emitida.
- **Validar código de benefício** – quando esse parâmetro é ativado, a compatibilidade entre o CST e o código de isenção ou de benefício de imposto de ICMS é validada quando os documentos fiscais são lançados.

> [!IMPORTANT]
> Ao ativar o parâmetro **Validar código de benefício**, você recebe a seguinte mensagem: "Deseja copiar os códigos de tributação dos tipos de código de benefício para o código de ajuste para o estado 'XX'?" Esta mensagem é mostrada porque uma versão do recurso **Nota técnica NT 2019.001 v 1.10** foi usada anteriormente e os tipos de benefícios já foram inseridos na página **Tipo de benefícios**. No entanto, você pode converter os tipos de benefícios para códigos de ajuste. Se você selecionar **Sim** na caixa de mensagem, os dados existentes da página obsoleta **Tipos de códigos de benefícios** serão convertidos em registros na página **Ajuste e informações para documentos fiscais**.

Os parâmetros **Adicionar marcas isentas** e **Validar códigos de benefício** devem ser configurados para a mesma autoridade que está configurada no estabelecimento e a autoridade deve ser do mesmo estado do endereço do estabelecimento.

1. Acesse **Administração da organização \> Organizações \> Documentos fiscais eletrônicos \> Parâmetros de NF-e federal**.
2. Na guia **Serviços Web**, no campo **Autoridade**, selecione a mesma autoridade que está configurada no estabelecimento.
3. Na guia **Estados atendidos**, marque ou desmarque as caixas de seleção **Adicionar marcas de isenção** e **Validar códigos de benefício** de acordo com a legislação estadual.

![Configurações de estabelecimento fiscal e de autoridade.](media/bra_tax_benefits_from_NT2019_001_parameters.png)

## <a name="set-up-benefit-codes"></a>Configurar códigos de benefícios

Os códigos de benefício fornecidos pela tabela **cBenef x CST** devem ser inseridos como códigos de ajuste especiais no módulo **Livros fiscais**.

1. Acesse **Livros fiscais \> Configuração \> Códigos de ajuste do imposto \> Ajuste e informações de documentos fiscais**.
2. Selecione **Novo** para adicionar um código de ajuste e defina os seguintes valores:

    - **Tipo de imposto:** Selecione **ICMS**.
    - **Tabela 5.2:** Defina esta opção como **Sim**.
    - **Estado:** Selecione o estado da autoridade na página **Parâmetros federais de NF-e**.
    - **Classificação:** Selecione **8: Controle especial**.
    - **Código de ocorrência:** Insira a parte numérica do código de benefício fornecida pela tabela **cBenef x CST**.
    - **Código de ajuste:** Este código é formado pelo estado e pelo código de ocorrência. Esse código deve corresponder ao código de benefício fornecido pela tabela **cBenef x CST**.

![Propriedades dos códigos de ajuste.](media/bra_tax_benefits_from_NT2019_001_adjustment_codes.png)

Observe as seguintes propriedades especiais dos códigos de ajuste:

- **Código de ajuste literal** – defina esta opção como **Sim** somente em cenários em que você emite modelos de notas fiscais eletrônicas 55 e 65 que têm tributação regular sem nenhum benefício ou isenção, quando a tabela **cBenef x CST** requer ou permite que o código de ajuste seja usado como um valor fixo ou uma palavra literal, como "nulo" ou "sem BENEF", na marca **\<cBenef\>**.
- **Suprimir código** – defina esta opção como **Sim** somente em cenários nos quais você emite modelos de notas fiscais eletrônicas 55 e 65 que têm tributação regular sem nenhum benefício ou isenção, quando a tabela **cBenef x CST** requer ou permite que a marca **\<cBenef\>** vazia seja usada.

![Propriedades especiais dos códigos de ajuste.](media/bra_tax_benefits_from_NT2019_001_adjustment_codes_special_controls.png)

## <a name="set-up-taxation-code-by-benefit-code"></a>Configurar código de tributação por código de benefício

O código de tributação por código de benefício fornecidos pela tabela **cBenef x CST** deve ser inserido como código de ajuste no módulo **Livros fiscais**.

1. Acesse **Livros fiscais \> Configuração \> Códigos de ajuste do imposto \> Ajuste e informações de documentos fiscais**.
2. Selecione **Adicionar** para inserir **Código de tributação** para o código de ajuste.

![Guia de códigos de tributação na página Ajuste e informações para documentos fiscais.](media/bra_tax_benefits_from_NT2019_001_adjustment_codes_CST.png)

## <a name="set-up-benefit-codes-by-itemstate"></a>Configurar códigos de benefício por item/estado

Siga estas etapas para configurar regras para validar os códigos de benefício por CST para um determinado Estado, conforme descrito na tabela **cBenef x CST**.

1. Acesse **Imposto \> Configuração \> Imposto \> Código de benefício por item/estado**.
2. Selecione **Novo**.
3. Na página **Parâmetros federais de NF-e**, no campo **Estado**, selecione um valor.
4. Selecione **Adicionar** para informar uma nova relação.

![Campo de estado na página código de Benefício por item/estado.](media/bra_tax_benefits_from_NT2019_001_benefit_codes_per_item_state.png)

## <a name="validations-that-are-done-when-fiscal-documents-are-posted"></a>Validações efetuadas quando as notas fiscais são lançadas

Quando o parâmetro **Validar código de benefício** estiver habilitado na página **Parâmetros federais de NF-e**, o lançamento de modelos de documentos fiscais 55 e 65 é validado de acordo com as regras configuradas na página **Código de benefício por item/estado**.

A validação ocorre para as regras configuradas na página **Código de benefício por item/estado**, para as duas direções de notas fiscais (entrada e saída) e os dois tipos de emissores (estabelecimentos e terceiros).

- Quando a direção do documento fiscal é de saída, a configuração das regras do estado da autoridade deve ser definida na página **Parâmetros do estabelecimento**.
- Quando a direção do documento fiscal é de entrada, e o emissor do documento fiscal é o estabelecimento, a configuração das regras para o estado da autoridade também deve ser definida na página **Parâmetros do estabelecimento**.
- Quando a direção do documento fiscal é de entrada, e o emissor do documento fiscal é o terceiro, a configuração das regras deve ser feita em nível de estado do emissor do documento fiscal.

> [!IMPORTANT]
> Para Finance ou Supply Chain Management, depois de KB 4582589, a validação das notas fiscais de entrada durante o lançamento se tornou obsoleta e não é mais concluída por padrão quando a direção do documento fiscal é de entrada e o emissor do documento fiscal é um terceiro. No entanto, se você precisar continuar a validação, o recurso **FiscalDocumentNotSkipBenefitValidationIncomingThirdPartyFlight** deve ser ativado.

## <a name="validation-exceptions"></a>Exceções de validação

A Nota técnica NT 2019.001 especifica regras de exceção que são adotadas a critério de cada estado. Para obter mais informações sobre as regras de validação, consulte as regras N12-85, N12-86, N12-90, N12-94, N12-97 e N12-98 na nota técnica.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]