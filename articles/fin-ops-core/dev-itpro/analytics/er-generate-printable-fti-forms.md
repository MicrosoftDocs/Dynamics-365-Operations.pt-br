---
title: Gerar formulários de FTI imprimíveis
description: Este tópico explica como usar a estrutura de relatório eletrônico (ER) para gerar formulários de fatura de texto livre (FTI) imprimíveis como documentos do Microsoft Office.
author: NickSelin
manager: AnnBe
ms.date: 07/24/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: da671d7b9302f99fc71860cf41846290d74d11e1
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570677"
---
# <a name="generate-printable-fti-forms"></a>Gerar formulários de FTI imprimíveis

[!include[banner](../includes/banner.md)]

A estrutura de relatório eletrônico (ER) permite gerar formulários de fatura de texto livre (FTI) imprimíveis como documentos do Microsoft Office. Este tópico fornece informações sobre como criar suas próprias configurações, bem como detalhes de modelos de configuração disponíveis.

## <a name="overview"></a>Visão Geral

Além da capacidade existente de gerar formulários de FTI imprimíveis usando o Microsoft SQL Server Reporting Services (SSRS), agora é possível usar a estrutura de ER. Você pode gerenciar os formulários de FTI imprimíveis no Microsoft Office Excel e no Word. Você também pode modificar o layout, o fluxo de dados e a formatação para atender a requisitos específicos sem fazer alterações no código.

> [!NOTE]
> Para começar com uma visão geral das configurações de ER existentes para este exemplo de solução de formulários de FTI imprimíveis, você pode acessar diretamente a seção **Baixar modelo de configurações de ER para gerar formulários de FTI imprimíveis** posteriormente neste tópico.

## <a name="create-customized-configurations-for-fti-printable-forms"></a>Criar configurações personalizadas para formulários de FTI imprimíveis
Como parte de suas soluções personalizadas para formulários de FTI imprimíveis, você deve criar um conjunto de configurações de ER.

### <a name="configure-the-er-data-model"></a>Configurar o modelo de dados de ER
Seu aplicativo deve incluir o modelo de dados de ER contendo um modelo de dados que descreva o domínio comercial do faturamento do cliente. Como requisito, o nome do modelo de dados deve ser **CustomersInvoicing**. Para obter informações sobre como criar modelos de dados de ER, consulte [ER Criar modelo de dados de domínio específico](tasks/er-design-domain-specific-data-model-2016-11.md).

### <a name="configure-the-er-model-mapping"></a>Configurar o mapeamento de modelo de ER
Seu aplicativo deve incluir o mapeamento de ER do modelo de dados CustomersInvoicing. O mapeamento de modelo pode estar na configuração do modelo de dados de ER ou na configuração de mapeamento de ER. Contudo, o nome do descritor raiz do mapeamento de modelo deve ser **FreeTextInvoice**.

O mapeamento deve conter as seguintes fontes de dados:

- Tipo de fonte de dados: **Registros da tabela**

    - Essa fonte de dados deve ser chamada **CustInvoiceJour**.
    - Deve se referir à tabela do aplicativo CustInvoiceJour.
    - É usada no tempo de execução para passar do aplicativo para o modelo de ER mapeando a lista de faturas que foram selecionadas para impressão.

- Tipo de fonte de dados: **Objeto**

    - Essa fonte de dados deve ser chamada **PrintMgmtPrintSettingDetail**.
    - Deve se referir à classe do aplicativo **PrintMgmtPrintSettingDetail**.
    - É usada no tempo de execução para passar do aplicativo para o modelo de ER mapeando os detalhes das configurações de gerenciamento de impressão do formato de ER em execução.

Os detalhes da integração de aplicativo com a estrutura de ER podem ser encontrados na classe **ERPrintMgmtReportFormatSubscriber** (modelo de integração do pacote de aplicativos de ER) no código-fonte do aplicativo.

Para obter mais informações sobre a criação de mapeamentos de modelo de ER, consulte [Definir mapeamentos de modelos de ER e selecionar fontes de dados para eles](tasks/er-define-model-mapping-select-data-sources-2016-11.md).

### <a name="configure-the-er-format"></a>Configurar o formato de ER
Na instância do seu aplicativo, você deve ter a configuração de formato de ER que será usada para gerar formulários de FTI. 

> [!NOTE]
> Essa configuração de formato deve ser criada para o modelo de dados CustomersInvoicing e deve usar o mapeamento de modelo com o descritor raiz **FreeTextInvoice**.

Para obter informações sobre como configurar formatos de ER, consulte [ER Criar uma configuração de formato (novembro de 2016)](tasks/er-format-configuration-2016-11.md). Para obter informações sobre como criar formatos de ER para gerar relatórios no formato OpenXML, consulte [ER Criar uma configuração para gerar relatórios no formato OPENXML (novembro de 2016)](tasks/er-design-reports-openxml-2016-11.md).

## <a name="configure-print-management"></a>Configurar gerenciamento de impressão
Para gerar formulários de FTI usando a estrutura de ER, você pode atribuir os formatos de ER da mesma forma que você atribui relatórios de SSRS. Para associar o formato de ER a todos os FTIs de contas a receber, acesse **Contas a receber** \> **Configuração** \> **Formulários** \> **Configuração de formulário** \> **Geral** \> **Gerenciamento de impressão** \> **Fatura de texto livre** \> **Original**. Para associar o formato de ER a um cliente ou fatura específicos, siga estas etapas:

1. Acesse **Contas a receber** \> **Faturas** \> **Todas as faturas de texto livre**.
2. Selecione o FTI para associar o formato de ER e abra a página **Configuração de gerenciamento de impressão**.
3. Selecione o nível de documento para especificar o escopo das faturas para processamento.
4. Selecione o formato de ER especificado para o nível de documento.

![Configuração de gerenciamento de impressão](media/FTIbyGER-PMSetting.png)

> [!NOTE]
> Somente os formatos de ER que usam o descritor raiz **FreeTextInvoice** do modelo de dados **CustomersInvoicing** aparecem no campo **Pesquisa de formato de relatório** para o formato selecionado.

## <a name="generate-fti-forms"></a>Gerar formulários de FTI
Os formulários de FTI são gerados na estrutura de ER da mesma forma que os relatórios de SSRS são gerados.

Para gerar formulários de FTI, você pode selecionar faturas por intervalo ou por seleção. 

![Seleção de fatura](media/FTIbyGER-InvoiceSelection.png)

![Visualização de fatura](media/FTIbyGER-InvoiceExcelPreview.png)

Quando você usa formatos de ER para imprimir formulários de FTI dessa forma, os destinos padrão do arquivo de ER são usados. Você não pode alterar o destino. Para obter mais informações sobre como configurar os destinos de ER para formatos de ER, consulte [Destinos de ER (Relatórios eletrônicos)](electronic-reporting-destinations.md).

Você também pode gerar formulários de FTI ao lançar um FTI, ativando **Imprimir fatura** e desativando **Usar os destinos do gerenciamento de impressão**.

> [!NOTE]
> Quando você usa formatos de ER para imprimir formulários de FTI dessa forma, os destinos padrão do arquivo de ER são usados. Você pode alterar o destino padrão no tempo de execução se o destino já tiver sido configurado. Para alterar o destino, você deve ter o seguinte privilégio de segurança:
>
> - **Nome:** ERFormatDestinationRuntimeMaintain
> - **Rótulo:** manter destino de formato de relatório eletrônico durante o tempo de execução

![Destino de relatório eletrônico](media/FTIbyGER-ERFileDestinationSetting.png)

![Destino em formato de relatório eletrônico](media/FTIbyGER-ERFileDestinationUsage.png)

A estrutura de ER é compatível com os seguintes destinos para documentos gerados:

- **Arquivo baixado** – Os formulários gerados são oferecidos como downloads que você pode salvar usando o navegador.
- **Tela** – O Microsoft 365 Excel é usado para visualizar formulários de FTI gerados no formato Excel.
- Pasta do **SharePoint** – os formulários gerados são armazenados com base nas configurações da estrutura de gerenciamento de documentos.
- **Arquivo do aplicativo** – os formulários gerados são armazenados como anexos de registros de log de execução no Armazenamento do Microsoft Azure.
- **Email** – Os formulários gerados são enviados como anexos de email.

> [!NOTE]
> Você não pode enviar os formulários de FTI gerados diretamente para a impressora, porque atualmente não há suporte para a impressão direta que usa o Dynamics Printer Routing Agent.

## <a name="download-sample-er-configurations-to-generate-printable-fti-forms"></a>Baixar exemplo de configurações de ER para gerar formulários de FTI imprimíveis
Você pode baixar exemplos de configurações de ER para usar como um modelo para sua solução de FTI. As configurações são armazenadas na biblioteca de ativos compartilhados do Microsoft Dynamics Lifecycle Services (LCS). As configurações incluem:

- A configuração **Modelo de faturamento do cliente** contém o mapeamento exigido do modelo de dados e do modelo.
- A configuração **Relatório de FTI do cliente (GER)** contém o formato de exemplo.

> [!NOTE]
> Essas configurações foram criadas como exemplos para ajudar a esclarecer possíveis cenários. O futuro dessas configurações depende dos resultados dessa avaliação e de qualquer feedback recebido.

### <a name="features-that-are-implemented-in-the-sample-er-format"></a>Recursos implementados no exemplo de formato de ER
Na configuração do exemplo de formato de ER, um arquivo do Excel é usado como modelo para gerar formulários de FTI.

![Designer de formato](media/FTIbyGER-ERFormat.png)

Atualmente, esse exemplo de formato de ER é compatível com os seguintes recursos para gerar formulários de FTI:

- Os formulários de FTI são gerados para as faturas originais lançadas e para as faturas originais ainda não publicadas. Não há suporte para faturas corrigidas e notas de crédito.
- Os formulários de FTI são gerados no idioma da fatura. O formato dos valores e datas nos formulários gerados é baseado nas configurações da localidade do cliente do usuário.
- As faturas geradas mostrarão notificações de indisponibilidade de dados se não houver linhas nas faturas processadas.
- Os cabeçalhos de faturas geradas são baseados no formato do papel que foi selecionado para o formulário de FTI na página **Parâmetros de contas a receber**. Os detalhes da empresa aparecem no cabeçalho do formulário de faturas geradas somente se o formato do papel estiver em branco.
- Os formulários de faturas geradas mostraram números de isenção de impostos da empresa e do cliente quando a opção apropriada foi selecionada para o formulário de FTI na página **Parâmetros de contas a receber**.
- As seções de linhas de faturas geradas e totais de fatura mostram os detalhes monetários da fatura padrão na moeda de registro da fatura.
- A seção de totais de faturas geradas pode mostrar detalhes monetários na moeda euro e na moeda de registro da fatura quando a opção **Imprimir o valor na moeda representando o euro** estiver habilitada na página **Parâmetros de contas a receber**.
- Os formulários de faturas geradas mostram as notas de fatura de processo disponíveis, com base nas configurações na página **Parâmetros de contas a receber**. As notas são incluídas para a fatura inteira e para cada linha da fatura.
- Os formulários de faturas geradas incluem notas para o formulário de FTI do cliente e o idioma da fatura de processamento quando foram configurados na lista de notas do formulário de AR.
- Dependendo das configurações de gerenciamento de impressão, as faturas geradas incluem texto de rodapé personalizado quando foi configurado para o idioma da fatura, o formato de ER e o escopo do documento de FTI.
- A seção de totais de formulários de faturas geradas inclui todas as informações sobre desconto à vista disponíveis.
- A seção de agenda de pagamento dos formulários de faturas geradas inclui todos os detalhes sobre agenda de pagamento disponíveis.
- A seção de marcação dos formulários de faturas geradas inclui todas as transações de encargos disponíveis.
- Os formulários de faturas geradas incluem detalhes sobre impostos, com base na configuração **Especificação de imposto** na página **Parâmetros de contas a receber**. Esta seção pode mostrar detalhes sobre impostos apenas na moeda de registro da fatura ou na moeda de registro da fatura e na moeda contábil da empresa ao mesmo tempo.
- Os formulários de faturas geradas mostram detalhes da notificação de débito direto. Por exemplo, mostram quando o método de pagamento com a ID da carta de ordem de débito direto foi selecionado para a fatura, quando a fatura de processamento foi registrada na moeda euro e quando a ID da carta de ordem de débito direto foi definida para a fatura.
- As faturas geradas mostram todos os detalhes sobre pagamento antecipado disponíveis para faturas lançadas.
- Formulários de faturas geradas podem ser enviados a um cliente de fatura como anexo de email. O destino adequado do arquivo de ER deve ser configurado para o formato de ER sendo usado.

### <a name="countryregion-specific-features"></a>Recursos específicos do país/região 
Os seguintes recursos específicos do país/região estão incluídos no exemplo de formato de ER para mostrar como requisitos específicos podem ser tratados nas configurações de ER.

#### <a name="norway"></a>Noruega
O termo Registro da empresa é colocado no cabeçalho do formulário de faturas geradas quando a fatura é processada para uma entidade legal configurada da seguinte maneira:

- O contexto do país/região da Noruega é usado.
- O parâmetro **Imprimir Foretaksregisteret** está ativo em documentos de vendas.

#### <a name="spain"></a>Espanha
O termo **Regime especial para método contábil de caixa** é colocado no cabeçalho do formulário de faturas geradas quando a fatura é processada para uma entidade legal configurada da seguinte maneira:

- O contexto do país/região da Espanha é usado.
- O regime especial para o método de contabilidade de pagamento à vista é ativado na data de processamento da fatura.

Quando detalhes de desconto à vista, como o valor do desconto à vista e o valor líquido da linha da fatura, estiverem disponíveis, serão apresentados na seção de totais da fatura do formulário de faturas geradas no momento em que este tiver sido processado para uma entidade legal configurada da seguinte maneira:

- O contexto do país/região da Espanha é usado.
- **O desconto à vista é aplicado na fatura** é ativado na opção de fatura (**Parâmetros da contabilidade** \> **Seção de imposto**).

#### <a name="italy"></a>Itália
A marca de descontos sobre mercadorias é incluída nas linhas de fatura da fatura gerada quando está sendo processada para uma entidade legal configurada usando o contexto do país/região da Itália.

#### <a name="finland"></a>Finlândia
Além do formulário de faturas geradas, guias de transferência de dinheiro por débito direto podem ser criadas da seguinte maneira:

- Para a entidade legal que usa o contexto do país/região da Finlândia e que tem pelo menos uma conta bancária marcada como **Conta de débito direto** e **Código de barras do banco**. 
- Para uma fatura marcada como necessária para o anexo do pagamento associado **Finlandês**.

![Guia de débito direto](media/FTIbyGER-GiroSlip.PNG)

> [!NOTE]
> O exemplo de formato de ER foi configurado para gerar opcionalmente os comprovantes de transferência de dinheiro por débito direto na planilha separada.

> [!NOTE]
> Primeiro, você deve instalar a fonte usada para gerar o código de barras na máquina local, no qual o formulário de faturas geradas no formato Excel será visualizado.

### <a name="use-the-sample-er-format-to-configure-email-destinations"></a>Usar o exemplo de formato de ER para configurar destinos de email
Use os seguintes elementos do exemplo de formato de ER para configurar destinos de email:

- O endereço de email de um contato do cliente pode ser acessado por meio da seguinte expressão de ER: **model.InvoiceBase.Contact.ElectronicMail**.
- O texto do assunto do email pode ser acessado por meio da seguinte expressão de ER: **Emailing.TxtToUse.Subject**.
- O texto do corpo do email pode ser acessado por meio da seguinte expressão de ER: **Emailing.TxtToUse.Body**.

![Configurações de destino](media/FTIbyGER-ERFileDestinationSettingEmail.png)

O texto padrão do assunto e do corpo do email é definido no exemplo de formato de ER. O idioma dependerá dos rótulos do formato. Esse texto padrão será usado para emails se um modelo de email da organização personalizado com a ID **ERFTITMP** tiver sido adicionado.

> [!NOTE]
> A ID de modelo de email **ERFTITMP** foi definida no exemplo de formato de ER. Pode ser alterada conforme necessário em um novo formato de ER criado a partir desse exemplo de formato.

Se o modelo de email da organização com a ID **ERFTITMP** tiver sido adicionado para a entidade legal em relação à qual você está processando a fatura, o modelo do texto de assunto e corpo do email será usado para gerar o email. 

![Modelos de email da organização](media/FTIbyGER-EmailTemplate.png)

![Carregar modelo de email](media/FTIbyGER-EmailTemplateBody.png)

A expressão de ER **Emailing.TxtToUse.Subject** do exemplo de formato de ER está configurada para substituir qualquer ocorrência do espaço reservado %1 pela ID da fatura de processamento.

A expressão **Emailing.TxtToUse.Body** do exemplo do formato está configurada para as seguintes substituições de espaços reservados:

- "%1" é substituído pelo nome da pessoa de contato do cliente.
- "%2" é substituído pelo nome da empresa.
- "%3" é substituído pelo nome do cliente.
- "%4" é substituído pelo nome da pessoa de contato da empresa.
- "%5" é substituído pelo cargo da pessoa de contato da empresa.
- "%6" é substituído pelo endereço de email da pessoa de contato da empresa.

![Email](media/FTIbyGER-Email.PNG)

## <a name="additional-resources"></a>Recursos adicionais
[Visão geral de Relatório eletrônico (ER)](general-electronic-reporting.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]