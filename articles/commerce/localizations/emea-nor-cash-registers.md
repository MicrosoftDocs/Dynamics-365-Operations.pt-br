---
title: Funcionalidade de caixa registradora para a Noruega
description: Este artigo fornece uma visão geral da funcionalidade de caixa registradora disponível para a Noruega no Microsoft Dynamics 365 Commerce e fornece diretrizes para a configuração da funcionalidade.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2017-10-31
ms.openlocfilehash: 42eda805646dbb30b40528254a3137102e3075e4
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292727"
---
# <a name="cash-register-functionality-for-norway"></a>Funcionalidade de caixa registradora para a Noruega

[!include[banner](../includes/banner.md)]

Este artigo fornece uma visão geral da funcionalidade de caixa registradora disponível para a Noruega no Dynamics 365 Commerce. Ele também fornece diretrizes para a configuração da funcionalidade. A funcionalidade consiste nas seguintes partes:

- Os recursos de ponto de venda (PDV) comuns disponíveis aos clientes em todos os países ou regiões. Os exemplos incluem uma opção que permite impedir que uma cópia de um recibo seja impressa mais de uma vez.
- Recursos específicos da Noruega, como assinaturas digitais para transações de vendas.

## <a name="overview-of-cash-register-functionality-for-norway"></a>Visão geral da funcionalidade de caixa registradora da Noruega

### <a name="common-pos-features"></a>Recursos de POS comuns

Para saber mais sobre os recursos de PDV disponíveis para os clientes em todos os países ou regiões, consulte [Recursos de ajuda do Dynamics 365 Retail](../index.md).

Os seguintes recursos de localização de PDV que foram implementados anteriormente e disponibilizados para clientes em todos os países ou regiões podem agora ser usados especificamente para a Noruega:

- **Imprimir campos de texto em um recibo em um tamanho de fonte grande.** Você pode usar o parâmetro **Tamanho da fonte** no Designer de formato de recibo para especificar que o tamanho de fonte grande deve ser usado para um campo no formato do recibo. (O tamanho de fonte grande é aproximadamente o dobro do tamanho de fonte normal.) Por exemplo, você pode usar esse parâmetro para imprimir o indicador de "Cópia" em uma cópia de um recibo em caracteres grandes.
- **Registrar a impressão das cópias de recibo no log de eventos de auditoria do PDV.** Você pode usar o parâmetro **Auditoria** no perfil de funcionalidade de PDV para permitir que cópias de recibos sejam impressas e outros eventos de auditoria de PDV sejam registrados. Os eventos de auditoria são registrados no banco de dados do canal e no headquarters. Você pode exibir os eventos de auditoria na página **Eventos de auditoria**.
- **Impedir que uma cópia de um recibo seja impressa mais de uma vez.** Quando o parâmetro **Auditoria** no perfil de funcionalidade de PDV é habilitado, a permissão de PDV **Permitir impressão de cópias de recibo** controla se cópias de recibos podem ser impressas. Também há uma opção que permite impedir que uma cópia de um recibo seja impressa mais de uma vez.

Além disso, o seguinte recurso de PDV foi implementado para a Noruega, mas disponibilizado para clientes em todos os países ou regiões:

- **Registrar eventos adicionais no log de eventos de auditoria do PDV.** Se o parâmetro **Auditoria** no perfil de funcionalidade de PDV estiver habilitado, os eventos a seguir serão registrados no log de eventos de auditoria de PDV:

    - Verificações de preço
    - Substituições de imposto
    - Correções nas quantidades de linhas
    - Limpar transações do banco de dados do canal

### <a name="norway-specific-pos-features"></a>Recursos de PDV específicos da Noruega

Os seguintes recursos de PDV específicos da Noruega são habilitados quando o parâmetro **Código ISO** no perfil de funcionalidade de PDV está definido como **Não**.

#### <a name="digital-signing-of-sales-transactions"></a>Assinatura digital de transações de vendas

Todas as transações de vendas são assinadas digitalmente. A assinatura é criada e registrada no diário de transações do PDV ao mesmo tempo em que a transação é finalizada. A assinatura também está disponível no diário que é exportado para fins de auditoria.

Somente as transações de vendas à vista são assinadas. Veja a seguir alguns exemplos de transações que são excluídas do processo de assinatura:

- Pagamentos antecipados (depósito na conta do cliente)
- Pagamentos antecipados para ordens de venda (depósito de ordem de cliente)
- Emitir um cartão-presente
- Transações não relacionadas a vendas (entrada de flutuação, remoção de forma de pagamento, etc.)

Os dados assinados são uma sequência de caracteres de texto que consiste nos campos de dados a seguir. Os campos são separados por ponto e vírgula.

1. Assinatura anterior para o mesmo PDV (um zero \[**0**\] é usado para a primeira transação).
2. Data da transação
3. Hora da transação
4. Número sequencial de transação assinada
5. Valor da transação incluindo o imposto
6. Valor da transação excluindo o imposto

O processo de assinatura digital usa uma chave RSA de 1024 bits que tem uma função de hash SHA-1 (RSA-SHA1-1024). Um certificado que é instalado no Commerce Scale Unit é usado para assinar. O identificador exclusivo do certificado (volume) é registrado em conjunto com a assinatura.

A assinatura é armazenada no banco de dados de armazenamento e no banco de dados do headquarters (HQ) juntamente com os dados da transação. Você pode visualizar a assinatura da transação juntamente com os dados da transação usados para gerá-la na guia rápida **Transações fiscais** da página **Transações da loja**.

#### <a name="receipts"></a>Recebimentos

Os recibos da Noruega podem incluir informações adicionais implementadas usando campos personalizados:

- **Título do recibo** – Você pode adicionar um campo a um layout do formato de recibo para identificar o tipo de recibo. Por exemplo, um recibo de vendas incluirá o texto "Recibo de vendas".
- **Número sequencial da transação assinada** – O número sequencial de uma transação assinada pode aparecer no recibo para associar um recibo impresso a uma assinatura digital no banco de dados.
- **Totais do recibo** – Campos personalizados para totais do recibo, exceto valores não relacionadas a vendas de valores do total de transações. Os valores de não vendas incluem os valores das seguintes operações:

    - Pagamentos antecipados (depósito na conta do cliente)
    - Pagamentos antecipados para ordens de venda (depósito de ordem de cliente)
    - Emitir um cartão-presente
    - Adicionar fundos a um cartão-presente

#### <a name="x-and-z-reports"></a>Relatórios X e Z

As informações incluídas nos relatórios X e Z são baseadas nos requisitos da Noruega. Por exemplo, os valores de **Total de vendas à vista** incluem somente valores para transações de vendas à vista e excluem operações de emissão de cartões-presente e pagamentos antecipados. O total de vendas à vista também é listada de acordo com o grupo de itens e a forma de pagamento. Além disso, os valores cumulativos de **Total geral de vendas** e **Total geral de devoluções** são mantidos e impressos.

#### <a name="saf-t-cash-register-audit-file"></a>Arquivo de auditoria de caixa registradora SAF-T

Você pode exportar o diário de transações de PDV no formato predefinido de caixa registradora de Arquivo de Auditoria Padrão para Impostos (SAF-T). O arquivo de auditoria inclui informações sobre a organização, dados mestres relevantes (como grupos de itens, itens e códigos de impostos), dados de transações de vendas à vista com assinaturas para essas transações, dados de eventos não relacionados a vendas e dados de relatórios de fim de datas.

O arquivo de auditoria pode ser exportado para os seguintes cenários:

- Por loja
- Todas as lojas
- Por terminal
- Todos os terminais

Você também pode enviar um relatório de uma entidade legal em nome de outra entidade legal. Nesse caso, você deve executar a exportação da entidade legal operacional e especificar a entidade legal de relatório como o remetente do relatório.

O formato da caixa registradora SAF-T é implementado no headquarters usando o [Relatório eletrônico](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md). 

## <a name="setting-up-commerce-for-norway"></a>Configurar o Commerce para a Noruega

Esta seção descreve as configurações específicas e recomendadas para a Noruega. Para obter mais informações, consulte [Recursos de ajuda do Dynamics 365 Retail](../index.md).

Para usar a funcionalidade específica da Noruega, você deve executar estas tarefas:

- Defina o campo **País/região** como **NOR** (Noruega) no endereço principal da entidade legal.
- Defina o campo **Código ISO** como **NO** (Noruega) no perfil da funcionalidade de PDV de todas as lojas que está na Noruega.

Você também deve especificar as seguintes configurações para a Noruega.

### <a name="set-up-the-legal-entity"></a>Configurar a entidade legal

Verifique se o nome da entidade legal foi especificado. Esse nome será impresso nos relatórios X e Z.

Além disso, na guia rápida **Informações de conta bancária**, no campo **Número do banco**, especifique o número da organização.

### <a name="set-up-value-added-tax-vat-per-norwegian-requirements"></a>Configurar imposto sobre valor agregado (IVA) de acordo com requisitos da Noruega


Você deve criar códigos de impostos, grupos de impostos e grupos de impostos de item. Você também deve configurar informações de impostos para produtos e serviços. Para obter mais informações sobre como configurar e usar impostos, consulte [Visão geral de imposto](../../finance/general-ledger/indirect-taxes-overview.md).

Você também deve especificar grupos de impostos e habilitar a opção **Preços incluem o imposto** para as lojas na Noruega.

### <a name="set-up-functionality-profiles"></a>Configurar perfis de funcionalidade

Você deve habilitar a auditoria e configurar a numeração de recibo.

### <a name="update-pos-permissions-groups-and-individual-permission-settings-for-store-workers"></a>Atualizar grupos de permissões de PDS e configurações de permissões individuais para trabalhadores da loja

Defina a permissão **Permitir impressão de cópia de recibo** para um valor apropriado:

- **Permitir sempre** – O operador pode imprimir uma cópia de um recibo várias vezes.
- **Permitir somente uma vez** – O operador pode imprimir uma cópia de um recibo somente uma vez.
- **Permitir somente uma vez e somente se o BD da sede estiver disponível** – O operador poderá imprimir uma cópia de um recibo somente uma vez e somente se o banco de dados da sede estiver disponível por meio do Commerce Data Exchange: Real-time Service, para que o sistema possa verificar se nenhuma cópia do recibo foi impressa anteriormente nas lojas.
- **Nunca** – O operador não pode imprimir uma cópia de um recibo.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Configurar campos personalizados para que possam ser usados em formatos de recibos de vendas

Na página **Texto do idioma**, adicione os seguintes registros para os rótulos dos campos personalizados nos layouts de recibo. Os valores **ID de idioma**, **ID do texto** e **Texto** mostrados na tabela são apenas exemplos. Você pode alterá-los para atender aos seus requisitos.

| ID do Idioma | Texto                   | ID do texto |
|-------------|------------------------|---------|
| pt-BR       | Título do recebimento          | 900011  |
| pt-BR       | É cartão-presente           | 900012  |
| pt-BR       | Total (vendas)          | 900013  |
| pt-BR       | Imposto total (vendas)      | 900014  |
| pt-BR       | Total com imposto (vendas) | 900015  |
| pt-BR       | Valor do imposto (vendas)     | 900016  |
| pt-BR       | ID da transação à vista    | 900017  |

Na página **Campos personalizados**, adicione os seguintes registros para os campos personalizados nos layouts de recibo. Observe que os valores de **ID de texto da legenda** devem corresponder aos valores de **ID de texto** especificados na página **Texto do idioma**.

| Nome                            | Tipo    | ID do texto da legenda |
|---------------------------------|---------|-----------------|
| ReceiptTitle                    | Recebimento | 900011          |
| IsGiftCard                      | Recebimento | 900012          |
| SalesTotalExt                   | Recebimento | 900013          |
| TaxTotalExt                     | Recebimento | 900014          |
| TotalWithTaxExt                 | Recebimento | 900015          |
| AmountPerTaxExt                 | Recebimento | 900016          |
| CashTransactionSequentialNumber | Recebimento | 900017          |

> [!NOTE]
> É importante que você especifique os nomes de campos personalizados corretos, conforme listados na tabela acima. Um nome de campo personalizado incorreto causará a falta de dados em recibos.

### <a name="configure-receipt-formats"></a>Configurar formatos de recibo

Para todos os formatos de recibo necessários, altere o valor do campo **Comportamento de impressão** para **Sempre imprimir** para o formato de recibo.

No Designer de formato de recibo, adicione os seguintes campos personalizados às seções de recibo apropriadas. Os nomes de campo correspondem aos textos do idioma que você definiu na seção anterior.

1. Cabeçalho:

    - **Título do recibo** – Este campo identifica o tipo de recibo.
    - **ID da transação à vista** – Este campo imprime o número sequencial da transação à vista assinada.

2. Linhas:

    - **É um cartão-presente** – Este campo marca a linha de recibo como relacionada à operação Emitir cartão-presente ou Adicionar cartão-presente.

3. Rodapé:

    - **Total (vendas)** – Este campo imprime o valor total de vendas de à vista do recibo. O valor não inclui imposto. Pagamentos antecipados e operações de cartão-presente não são incluídos.
    - **Total de impostos (vendas)** – Este campo imprime o valor total de impostos para vendas à vista. Pagamentos antecipados e operações de cartão-presente não são incluídos.
    - **Total com impostos (vendas)** – Este campo imprime o valor total de vendas de à vista do recibo. O valor inclui imposto. Pagamentos antecipados e operações de cartão-presente não são incluídos.
    - **Valor de impostos (vendas)** – Este campo imprime o valor de impostos para vendas à vista de acordo com o código de imposto. Pagamentos antecipados e operações de cartão-presente não são incluídos.

Para mais informações sobre como trabalhar com formatos de recibo, consulte [Configurar e criar formatos de recibo](../receipt-templates-printing.md).

### <a name="configure-the-saf-t-cash-register-export-format"></a>Configurar o formato de exportação da caixa registradora SAF-T

A configuração da caixa registradora SAF-T está disponível para download no Microsoft Dynamics Lifecycle Services (LCS). Para obter mais informações, consulte [Importar configurações do ER (Relatório eletrônico)](../../fin-ops-core/dev-itpro/analytics/electronic-reporting-import-ger-configurations.md). Você deve baixar as seguintes configurações:

- **Dados do canal de varejo.versão.1** – A configuração do modelo de dados.
- **Dados do canal de varejo do DMM.versão.1.14** – A configuração do mapeamento do modelo de dados.
- **Número da caixa registradora SAF T.versão.1.20** – A configuração de formato.

Depois de importar as configurações, na página **Parâmetros do Commerce**, na guia **Documentos eletrônicos**, no campo **Formato de exportação da caixa registradora SAF-T**, selecione o nome da configuração de formato que foi importada.

Você também deve mapear dados mestres necessários para códigos padrão SAF-T predefinidos. Para obter mais informações, consulte a documentação da caixa registradora SAF-T fornecida pela administração de imposto da Noruega. Para criar o mapeamento, você deve definir o novo campo **Código da caixa registradora SAF-T** nas seguintes páginas:

- Grupos de itens
- Formas de pagamento
- Códigos de imposto

### <a name="configure-channel-components"></a>Configurar os componentes de canal

Para habilitar a funcionalidade específica da Noruega, você deve configurar os componentes de canal. Para obter mais informações, consulte as [diretrizes de implantação](emea-nor-fi-deployment.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
