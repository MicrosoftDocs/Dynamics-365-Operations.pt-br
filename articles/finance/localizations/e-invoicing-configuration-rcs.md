---
title: Configurar o Faturamento eletrônico no Regulatory Configuration Services (RCS)
description: Este tópico explica como configurar o Faturamento eletrônico no Regulatory Configuration Services (RCS) do Dynamics 365.
author: gionoder
ms.date: 05/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 6c1d309744c4c8dd0d17f5259551d31c257ede61
ms.sourcegitcommit: 633d51834d7d29b745824924315a3898dc471f1a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "6075134"
---
# <a name="configure-electronic-invoicing-in-regulatory-configuration-services-rcs"></a>Configurar o Faturamento eletrônico no Regulatory Configuration Services (RCS)

[!include [banner](../includes/banner.md)]

Este tópico fornece informações sobre os recursos de configuração do Faturamento eletrônico no Regulatory Configuration Services (RCS) do Dynamics 365.

É por meio dos recursos de configuração que o Faturamento eletrônico ajuda você a atender aos requisitos comerciais e regulatórios das faturas eletrônicas sem precisar de codificação. Nos cenários em que as faturas eletrônicas devem ser aprovadas eletronicamente por serviços Web, os recursos de configuração também ajudam a atender aos requisitos de troca de mensagens com serviços Web, sem códigos.

## <a name="electronic-reporting"></a>Relatório eletrônico

O Relatório Eletrônico (ER) oferece suporte ao Faturamento eletrônico.

O mapeamento e os formatos de modelo de dados são componentes configuráveis criados e mantidos pelo ER e usados no Faturamento eletrônico. O designer de formato ER é a ferramenta para criar e manter formatos de arquivo. Ele é usado para configurar os recursos de faturamento eletrônico.

Para obter mais informações, consulte [Visão geral de Relatório Eletrônico (ER)](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

## <a name="electronic-invoicing-features"></a>Recursos do faturamento eletrônico

Os recursos de faturamento eletrônico são responsáveis pela geração de faturas eletrônicas por meio do Faturamento eletrônico. Eles encapsulam as regras de configuração e as usam para processar os dados que o Microsoft Dynamics 365 Finance e o Dynamics 365 Supply Chain Management enviam para o Faturamento eletrônico e para faturas eletrônicas.

Os recursos também dão suporte a cenários em que a conformidade com especificações de formato de arquivo é necessária e a saída é um arquivo eletrônico autônomo. Na maioria dos casos, as especificações de formato de arquivo são publicadas pela autoridade fiscal.

Finalmente, os recursos dão suporte à troca de mensagens com serviços Web externos que são hospedados pela autoridade fiscal ou por alguma parte credenciada, e solicitações para autorização ou um carimbo de aprovação na fatura eletrônica.

### <a name="availability-of-electronic-invoicing-features"></a>Disponibilidade de recursos de faturamento eletrônico

A disponibilidade dos recursos de faturamento eletrônico depende do país ou região. Embora alguns recursos estejam geralmente disponíveis, outros estão na versão preliminar.

#### <a name="generally-available-features"></a>Recursos geralmente disponíveis

A tabela a seguir mostra os recursos de faturamento eletrônico que estão geralmente disponíveis.

| País/região | Nome do recurso                         | Documento comercial |
|----------------|--------------------------------------|-------------------|
| Egito          | Fatura eletrônica egípcia (EG) | Faturas de vendas e de projetos |

#### <a name="preview-features"></a>Recursos de versão preliminar

A tabela a seguir mostra os recursos de faturamento eletrônico que estão atualmente na versão preliminar.

| País/região | Nome do recurso                         | Documento comercial |
|----------------|--------------------------------------|-------------------|
| Áustria        | Faturas eletrônicas austríacas (AT)    | Faturas de vendas e de projetos |
| Bélgica        | Fatura eletrônica belga (BE)      | Faturas de vendas e de projetos |
| Brasil         | NF-e brasileira (BR)                  | Modelo de nota fiscal 55, cartas de correção, cancelamentos e descartes |
| Brasil         | NFS-e ABRASF Curitiba brasileira (BR) | Notas fiscais de serviço |
| Dinamarca        | Fatura eletrônica dinamarquesa (DK)       | Faturas de vendas e de projetos |
| Estônia        | Fatura eletrônica estoniana (EE)     | Faturas de vendas e de projetos |
| Finlândia        | Fatura eletrônica finlandesa (FI)      | Faturas de vendas e de projetos |
| França         | Fatura eletrônica francesa (FR)       | Faturas de vendas e de projetos |
| Alemanha        | Fatura eletrônica alemã (DE)       | Faturas de vendas e de projetos |
| Itália          | FatturaPA (IT)                       | Faturas de vendas e de projetos |
| México         | Mexicano CFDI (MX)                    | Faturas de venda, guias de remessa, transferências de estoque, complementos de pagamento e cancelamentos |
| Países Baixos    | Fatura eletrônica holandesa (NL)        | Faturas de vendas e de projetos |
| Noruega         | Fatura eletrônica norueguesa (NO)    | Faturas de vendas e de projetos |
| Espanha          | Fatura eletrônica espanhola (ES)      | Faturas de vendas e de projetos |
| Europa         | Fatura eletrônica PEPPOL            | Faturas de vendas e de projetos PEPPOL |

### <a name="configurable-components-of-electronic-invoicing-features"></a>Componentes configuráveis de recursos de faturamento eletrônico

Os recursos de faturamento eletrônico consistem nos seguintes grupos de componentes configuráveis:

- **Formatos** – permitem que você configure o que o Faturamento eletrônico deve gerar quando um documento eletrônico se torna uma fatura eletrônica. Os formatos incluem a configuração de formato para a fatura eletrônica e para os arquivos e mensagens usados para enviar solicitações e receber respostas quando a comunicação com um serviço Web externo é necessária.
- **Ações** – as ações permitem que você configure como o Faturamento eletrônico gera a transformação de um documento eletrônico que o Finance e o Supply Chain Management enviaram em uma fatura eletrônica.
- **Regras de aplicabilidade** – permitem configurar o contexto que o Faturamento eletrônico deve considerar para processar um recurso de faturamento eletrônico.
- **Variáveis** – as variáveis permitem que você configure o suporte para a construção da lógica de configuração. As variáveis podem funcionar como a entrada de valores para executar uma ação específica. Como alternativa, elas podem funcionar como uma troca de valores entre o Finance and o Supply Chain Management e o Faturamento eletrônico.
- **Mapeamento de modelos de documento eletrônico** – o mapeamento de modelos de documento eletrônico permite configurar o mapeamento do modelo de ER. O mapeamento do modelo define o mapeamento de dados da fatura abstrata que está integrada no Faturamento eletrônico quando os documentos eletrônicos são enviados.
- **Modelo de contexto de fatura** – o modelo de contexto de fatura permite configurar o modelo de contexto da fatura ER e definir o contexto de um recurso de faturamento eletrônico.
- **Tipos de respostas** – permitem que você configure o que o Faturamento eletrônico deve atualizar no Finance e no Supply Chain Management como resultado do processamento de faturas eletrônicas.

### <a name="formats"></a>Formatos

A lista a seguir mostra as configurações de formato ER disponíveis para os recursos de faturamento eletrônico.

#### <a name="austrian-at-electronic-invoices-sales-and-project-invoices-for-austria"></a>Faturas eletrônicas austríacas (AT): faturas de vendas e de projeto da Áustria

- Fatura de vendas OIOUBL
- Fatura de projeto OIOUBL
- Nota de crédito de vendas OIOUBL
- Nota de crédito de projeto OIOUBL

#### <a name="belgian-be-electronic-invoice-sales-and-project-invoices-for-belgium"></a>Fatura eletrônica belga (BE): faturas de vendas e de projeto da Bélgica

- Fatura de vendas UBL BE
- Fatura de projeto UBL BE
- Nota de crédito de projeto UBL BE
- Nota de crédito de venda UBL BE

#### <a name="brazilian-br-nf-e-nf-e-federal-brazil"></a>NF-e brasileira (BR): NF-e federal (Brasil)

- Formato de exportação de envio da NF-e (BR)
- Formato de exportação de carta de correção da NF-e (BR)
- Formato de exportação de cancelamento da NF-e (BR)
- Formato de exportação de descarte da NF-e (BR)

#### <a name="brazilian-nfs-e-br-nfs-e-abrasf-curitiba-city"></a>NFS-e brasileira (BR): NFS-e ABRASF cidade de Curitiba

- NFS-e ABRASF Curitiba (BR)
- NFS-e ABRASF Consulta Curitiba (BR)

#### <a name="danish-dk-electronic-invoice-sales-and-project-invoices-for-denmark"></a>Fatura eletrônica dinamarquesa (DK): faturas de vendas e de projeto da Dinamarca

- Fatura de vendas OIOUBL
- Fatura de projeto OIOUBL
- Nota de crédito de vendas OIOUBL
- Nota de crédito de projeto OIOUBL

#### <a name="dutch-nl-electronic-invoice-sales-and-project-invoices-for-netherlands"></a>Fatura eletrônica holandesa (NL): faturas de vendas e de projeto dos Países Baixos

- Fatura de venda UBL NL
- Fatura de projeto UBL NL
- Nota de crédito de projeto UBL NL
- Nota de crédito de venda UBL NL

#### <a name="egyptian-eg-electronic-invoice-sales-and-project-invoices-for-egypt"></a>Fatura eletrônica egípcia (EG): faturas de vendas e de projeto do Egito

- Fatura de venda (EG)(faturamento)
- Fatura de projeto (EG)(faturamento)

#### <a name="estonian-ee-electronic-invoice-sales-and-project-invoices-for-estonia"></a>Fatura eletrônica estoniana (EE): faturas de vendas e de projeto da Estônia

- Fatura de venda (EE)
- Fatura de projeto (EE)

#### <a name="finnish-fi-electronic-invoice-sales-and-project-invoices-for-finland"></a>Fatura eletrônica finlandesa (FI): faturas de vendas e de projeto da Finlândia

- Fatura de venda (FI)
- Fatura de projeto (FI)

#### <a name="french-fr-electronic-invoice-sales-and-project-invoices-for-france"></a>Fatura eletrônica francesa (FR): faturas de vendas e de projeto da França

- Fatura de venda UBL FR
- Fatura de projeto UBL FR
- Nota de crédito de projeto UBL FR
- Nota de crédito de venda UBL FR

#### <a name="german-de-electronic-invoice-sales-and-project-invoices-for-germany"></a>Fatura eletrônica alemã (DE): faturas de vendas e de projeto da Alemanha

- Fatura de venda (DE)
- Fatura de projeto (DE)

#### <a name="italian-it-electronic-invoice-sales-and-project-invoices-for-italy"></a>Fatura eletrônica italiana (IT): faturas de vendas e de projeto da Itália

- Fatura de venda (TI)
- Fatura de projeto (TI)

#### <a name="mexican-mx-cfdi-cfdi-for-mexico"></a>CFDI mexicano (MX): CFDI para México

- Formato de fatura CFDI (MX)
- Guia de remessa CFDI (MX)
- Transferência de estoque CFDI (MX)
- Formato de pagamento CFDI (MX)
- Formato de cancelamento de fatura CFDI (MX)

#### <a name="norwegian-no-electronic-invoice-sales-and-project-invoices-for-norway"></a>Fatura eletrônica norueguesa (NO): faturas de vendas e de projeto da Noruega

- Fatura de vendas OIOUBL
- Fatura de projeto OIOUBL
- Nota de crédito de vendas OIOUBL
- Nota de crédito de projeto OIOUBL

#### <a name="peppol-electronic-invoice-peppol-sales-and-project-invoices"></a>Fatura eletrônica de PEPPOL: faturas de vendas e de projetos PEPPOL

- Fatura de vendas PEPPOL
- Fatura de projeto PEPPOL
- Nota de crédito de vendas PEPPOL
- Nota de crédito de projeto PEPPOL

#### <a name="spanish-es-electronic-invoice-sales-and-project-invoices-for-spain"></a>Fatura eletrônica espanhola (ES): faturas de vendas e de projeto da Espanha

- Fatura de venda (ES)
- Fatura de projeto (ES)

Além das configurações de formato ER disponíveis pronto para uso com o serviço de faturamento eletrônico, você também pode criar suas próprias configurações de formato do ER. No entanto, as configurações de formato criadas para usar com os recursos de faturamento eletrônico não dão suporte à referência direta a tabelas do Supply Chain Management ou de qualquer metadado correspondente. Há suporte somente para referências ao mapeamento do modelo de ER.

### <a name="actions"></a>Ações

A tabela a seguir lista as ações disponíveis e indica se elas estão disponíveis no momento ou se ainda estão na versão preliminar.

| Ação                                        | descrição                                                                  | Disponibilidade         |
|-----------------------------------------------|------------------------------------------------------------------------------|----------------------|
| Transformar documento                            | Execute formato do Relatório Eletrônico para transformar o documento.                   | Geralmente disponível  |
| Assinar documento xml                             | Assine documentos xml com assinatura digital.                                   | Em versão preliminar           |
| Assine documento json para autoridade fiscal egípcia | Assine documentos json com assinatura digital para autoridade fiscal egípcia.       | Geralmente disponível  |
| Integrar com o serviço ETA egípcio           | Comunicar com a autoridade fiscal egípcia.                                     | Geralmente disponível  |
| Chamar serviço brasileiro da SEFAZ                  | Integrar com serviço brasileiro da SEFAZ para o envio de documento fiscal.       | Em visualização           |
| Chamar serviço PAC mexicano                      | Integrar com serviço PAC mexicano para envio do CFDI.                      | Em versão preliminar           |
| Processar resposta                              | Analise a resposta recebida da chamada do serviço Web.                     | Geralmente disponível  |
| Usar o MS Power Automate                         | Integração ao fluxo interno do Microsoft Power Automate.                       | Em versão preliminar           |

### <a name="applicability-rules"></a>Regras de aplicabilidade

As regras de aplicabilidade são cláusulas configuráveis definidas no nível do recurso de faturamento eletrônico. As regras são configuradas para fornecer um contexto para execução de recursos de faturamento eletrônico por meio do conjunto de recursos de faturamento eletrônico.

Quando um documento comercial do Finance ou do Supply Chain Management é enviado para o faturamento eletrônico, o documento comercial não tem uma referência explícita que permita a definição do recurso de faturamento eletrônico para chamar determinado recurso de faturamento eletrônico para processar o envio.

No entanto, quando configurado corretamente, o documento comercial contém os elementos necessários que permitem ao faturamento eletrônico decidir qual recurso de faturamento eletrônico deve ser selecionado e, depois, gerar a fatura eletrônica.

As regras de aplicabilidade permitem que o conjunto de recursos de faturamento eletrônico encontre os recursos de faturamento eletrônico exatos a serem usados para processar o envio. Isso é feito ao coincidir o conteúdo do documento comercial enviado com as cláusulas das regras de aplicabilidade.

Por exemplo, dois recursos de faturamento eletrônico com regras de aplicabilidade relacionadas são implantados no conjunto de recursos de faturamento eletrônico.

| Recurso de faturamento eletrônico | Regras de aplicabilidade        |
|------------------------------|--------------------------- |
| A                            | <p>País = BR</p><p>e</p><p>Entidade legal = BRMF</p>  |
| B                            | <p>País = MX</p><p>e</p><p>Entidade legal = MXMF</p>  |

Se um documento comercial do Finance ou do Supply Chain Management for enviado para o conjunto de recursos de faturamento eletrônico, o documento comercial conterá os seguintes atributos preenchidos como:

- País = BR
- Entidade legal = BRMF

O conjunto de recursos de faturamento eletrônico selecionará o recurso de faturamento eletrônico **A** para processar o envio e gerar a fatura eletrônica.

Da mesma forma, se o documento comercial contiver:

- País = MX
- Entidade legal = MXMF

O recurso de faturamento eletrônico **B** é selecionado para gerar a fatura eletrônica.

A configuração de regras de aplicabilidade não pode ser ambígua. Isso significa que dois ou mais recursos de faturamento eletrônico não podem ter as mesmas cláusulas; caso contrário, não haverá seleção. Se houver uma duplicação de recursos de faturamento eletrônico, para evitar ambiguidade, use cláusulas adicionais para permitir que o recurso de faturamento eletrônico seja definido para distinguir os dois recursos de faturamento eletrônico.

Por exemplo, considere o recurso de faturamento eletrônico **C**. Este recurso é uma cópia do recurso de faturamento eletrônico **A**.

| Recurso de faturamento eletrônico | Regras de aplicabilidade        |
|------------------------------|--------------------------- |
| A                            | <p>País = BR</p><p>e</p><p>Entidade legal = BRMF</p>  |
| C                            | <p>País = BR</p><p>e</p><p>Entidade legal = BRMF</p>  |

Neste exemplo, o recurso **C** ocorre antes de um envio de documento comercial que contém o seguinte:

- País = BR
- Entidade legal = BRMF

O recurso de faturamento eletrônico não pode distinguir qual recurso de faturamento eletrônico deve ser usado para processar o envio porque os envios contêm as mesmas cláusulas exatas.

Para criar uma distinção entre os dois recursos por meio de regras de aplicabilidade, uma nova cláusula deve ser adicionada a um dos recursos para permitir que o conjunto de recursos de faturamento eletrônico selecione o recurso de faturamento eletrônico apropriado.

| Recurso de faturamento eletrônico | Regras de aplicabilidade        |
|------------------------------|--------------------------- |
| A                            | <p>País = BR</p><p>e</p><p>Entidade legal = BRMF</p>  |
| C                            | <p>País = BR</p><p>e</p><p>Entidade legal = BRMF</p><p>e</p><p>Modelo=55</p>  |

Para dar suporte à criação de cláusulas mais complexas, os seguintes recursos estão disponíveis:

Operadores lógicos:
- E
- Ou

Tipos de operadores:
- Equal
- Not equal
- Greater than
- Less than
- Maior que ou igual a
- Menor que ou igual a
- Contém
- Começa com

Tipos de dados:
- Cadeia de caracteres
- Número
- Booliano
- Data 
- UUID

Capacidade de agrupar e desagrupar cláusulas.
O exemplo tem a aparência a seguir.

| Recurso de faturamento eletrônico | Regras de aplicabilidade        |
|------------------------------|--------------------------- |
| C                            | <p>País = BR</p><p>e</p><p>(Entidade legal = BRMF</p><p>ou</p><p>Modelo=55)</p>  |


## <a name="configuration-providers"></a>Provedores de configuração

Os provedores de configuração fornecem os recursos de faturamento eletrônico e seus componentes ER, como o mapeamento de modelos, a configuração de formato e o modelo de contexto. Eles publicam os recursos de faturamento eletrônico e os componentes ER no repositório global associado. A partir daí, outras organizações podem baixá-los.

Antes de configurar os recursos de faturamento eletrônico por meio do RCS, você deve configurar sua própria organização como um provedor de configuração no módulo de **Relatório eletrônico**. Para obter informações sobre como definir um provedor de configuração como **Ativo**, consulte [Criar provedores de configuração e marcá-los como ativos](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="viewing-electronic-invoicing-features-in-the-global-repository"></a>Exibir recursos de faturamento eletrônico no repositório global

Para procurar os recursos de faturamento eletrônico disponíveis no repositório global para um provedor de configuração específico, sincronize a instância RCS da sua organização. Depois que a sincronização é concluída, a lista de recursos de faturamento eletrônico disponíveis é atualizada.

## <a name="importing-electronic-invoicing-features"></a>Importar recursos de faturamento eletrônico

Antes de usar ou configurar os recursos de faturamento eletrônico, você deve importá-los para a instância RCS de sua organização. A operação de importação cria uma cópia local dos recursos e copia todos os artefatos ER que os recursos usam (por exemplo, configurações de formato e configurações de modelo) para a instância RCS da sua organização.

Você pode importar os recursos de faturamento eletrônico de qualquer provedor de configuração.

## <a name="creating-electronic-invoicing-features"></a>Criar recursos de faturamento eletrônico

Você pode criar um recurso de faturamento eletrônico do zero ou derivá-lo de outro recurso de faturamento eletrônico.

Ao criar um recurso de faturamento eletrônico do zero, você deve adicionar manualmente os componentes ER (por exemplo, configurações de versão do recurso e outras configurações, como a configuração da versão do recurso e a configuração do aplicativo). Quando você cria um recurso derivando-o de outro recurso, o novo recurso herda todas as configurações do original. 

## <a name="electronic-invoicing-feature-version"></a>Versão de recursos do faturamento eletrônico

Os recursos do faturamento eletrônico têm versões. Quando uma nova versão é criada, o número da versão é incrementado automaticamente. Uma data de "efetivação inicial" pode ser definida para a nova versão.

As versões do recurso de faturamento eletrônico seguem um ciclo de vida que tem até três status:

- **Rascunho** – se uma versão do recurso estiver neste status, você poderá editar seus atributos de configuração e qualquer um dos artefatos (por exemplo, configurações de formato de arquivo).
- **Concluir** – se uma versão do recurso estiver neste status, ela foi publicada no repositório global associado à sua organização. Não é mais possível editar a versão do recurso ou qualquer um dos componentes ER.
- **Publicado** – se uma versão do recurso estiver neste status, ela foi publicada no Faturamento eletrônico. Não é mais possível editar a versão do recurso ou qualquer um dos componentes ER.

### <a name="feature-configurations"></a>Configurações de recursos

Configurações de recursos contêm todas as configurações de formato ER que os recursos de faturamento eletrônico usam. Todos os arquivos eletrônicos que um recurso de faturamento eletrônico usa durante o processamento são provenientes das configurações de formato que foram adicionadas às configurações do recurso desse recurso.

Nas configurações do recurso, você pode acessar o designer de formato ER, que é a ferramenta ER usada para criar configurações de formato.

### <a name="feature-setup"></a>Configuração do recurso

As configurações de recursos são usadas em combinação com configurações de recursos. Cada configuração do recurso encapsula um conjunto de ações, regras de aplicabilidade e variáveis que fornecem o comportamento esperado para que um recurso de faturamento eletrônico possa atender a uma necessidade específica da fatura eletrônica.

### <a name="application-setup"></a>Configuração do aplicativo

A configuração do aplicativo deve ser associada a um aplicativo conectado criado previamente.

Por meio da configuração do aplicativo, você pode configurar a parte de um recurso de faturamento eletrônico que deve ser feita no Finance e no Supply Chain Management. Pelo menos três componentes configuráveis são obrigatórios, independentemente do recurso de faturamento eletrônico:

- **Nome da tabela** – a entidade no Finance e no Supply Chain Management que contém as faturas lançadas e na qual o recurso de faturamento eletrônico se baseia.
- **Contexto** – o nome do modelo de contexto de fatura configurado por meio de ER.
- **Mapeamento de documento comercial** – o nome do modelo de mapeamento de fatura configurado por meio de ER.

> [!IMPORTANT]
> A configuração inserida na configuração do aplicativo pode ser exibida no Finance e no Supply Chain Management. Acesse **Administração da organização \> Configuração \> Parâmetro de documento eletrônico**. Na guia **Documento eletrônico**, selecione **Implantar** e, depois, a opção **Aplicativo conectado**.

### <a name="deploying-feature-versions"></a>Implantar versões do recurso

No RCS, use o comando **Implantar** para direcionar a versão de um recurso de faturamento eletrônico. Selecione **Implantar** e uma das seguintes opções para definir o destino da implantação: 

- **Ambiente de serviço** – quando o destino da implantação é o ambiente de serviço, a versão do recurso de faturamento eletrônico é publicada no ambiente de serviço. O Faturamento eletrônico então estará pronto para receber e processar documentos eletrônicos enviados pelo Finance e pelo Supply Chain Management.
- **Aplicativo conectado** – quando o destino da implantação é o aplicativo conectado, a configuração fornecida pela configuração do aplicativo é gravada na instância do Finance e do Supply Chain Management que foi previamente associada a ele.

Somente as versões do recurso de faturamento eletrônico com o status **Concluído** podem ser implantadas em um ambiente de serviço ou em um aplicativo conectado.

### <a name="removing-feature-versions"></a>Remover versões do recurso

No RCS, use o comando **Cancelar implantação** para remover uma versão específica do recurso de faturamento eletrônico de um ambiente de serviço no Faturamento eletrônico.

> [!IMPORTANT]
> O comando **Cancelar implantação** só funciona em ambientes de serviço. Ele não remove versões do recurso de faturamento eletrônico de aplicativos conectados.

### <a name="rebasing-electronic-invoicing-features"></a>Trocar base de recursos de faturamento eletrônico

Quando um recurso de faturamento eletrônico deriva de outro, o comando **Trocar base** atualiza o recurso derivado com as alterações apresentadas no recurso original.

## <a name="additional-resources"></a>Recursos adicionais

- [Emitir faturas eletrônicas no Finance e no Supply Chain Management](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
