---
title: Intrastat polonês
description: Este tópico contém informações sobre o relatório Intrastat na Polônia.
author: andosip
ms.date: 11/09/2021
ms.topic: article
audience: Application User
ms.reviewer: kfender
ms.search.region: Global
ms.author: v-aosipov
ms.search.validFrom: ''
ms.openlocfilehash: 9564892f768adb8f48208fe10b31c7c6392a4567
ms.sourcegitcommit: f4823a97c856e9a9b4ae14116a43c87f9482dd90
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/09/2021
ms.locfileid: "7779898"
---
# <a name="polish-intrastat"></a>Intrastat polonês

[!include[banner](../includes/banner.md)]

A página **Intrastat** serve para gerar e relatar informações sobre o comércio entre os países da União Europeia (UE). A declaração Intrastat polonesa contém informações sobre o comércio de mercadorias para geração de relatórios.

Os seguintes campos estão incluídos na declaração Intrastat polonesa. Todos os campos são incluídos em entradas e despachos, exceto para **RodzajTransportu** (o modo de transporte) e **KrajPochodzenia** (o país ou região de origem) que não são incluídos nos despachos e **IdKontrahenta** (o número de IVA estrangeiro do cliente) que não está incluído nas entradas.

| Nome do campo | Descrição |
|-------------------------|-------------------------|
| Deklaracja Data | A data na qual o documento foi criado. |
| Miesiac | O mês de referência da declaração. |
| Rok | O ano de referência da declaração. |
| Numer | O número da declaração no período de referência. |
| Wersja | O número da versão da declaração. |
| NrWlasny | O identificador da declaração. O valor é gerado automaticamente. |
| Typ | A direção do relatório.</br><li>Para entradas, "P" é impresso.</li><li>Para despachos, "W" é impresso.</li> |
| Rodzaj | O tipo da declaração. O valor indica se o relatório é a declaração original ou uma declaração de correção. |
| UC | O código de unidade ao qual a declaração Intrastat é endereçada. O valor é especificado no campo **Número de isenção de imposto** na seção **Impostos** na guia **Agente** da página **Parâmetros de comércio exterior**. |
| Nazwa | O nome da empresa. |
| Miejscowosc, UlicaNumer, KodPocztowy | O endereço completo da entidade legal. |
| Nip | O número de identificação do imposto polonês (ID de imposto sobre valor agregado [IVA]). |
| Regon | O número de identificação da estatística (número da empresa) em polonês. |
| LacznaWartoscFaktur | A soma dos valores da fatura. |
| LacznaWartoscStatystyczna | A soma dos valores estatísticos. |
| LacznaLiczbaPozycji | O número total de itens de mercadorias. |
| PozId | O número consecutivo de um determinado item de mercadorias. |
| OpisTowaru | O nome comercial da mercadoria. |
| KrajPochodzeniaWysylki | O código ISO (International Organization for Standardization) para o país ou região da contrapartida. |
| WarunkiDostawy | O código Intrastat para as condições de entrega. |
| RodzajTransakcji | O código que indica a natureza da transação. As empresas polonesas usam códigos de transação de dois dígitos. |
| KodTowarowy | O código de mercadoria de oito dígitos de acordo com a Nomenclatura Combinada. |
| RodzajTransportu | O código Intrastat para o modo de transporte. |
| KrajPochodzenia | O código ISO para o país ou a região em que as mercadorias foram produzidas ou fabricadas. |
| MasaNetto | A massa líquida em quilogramas completas. |
| IloscUzupelniajacaJm | A quantidade na unidade de medida suplementar, em números inteiros. |
| WartoscFaktury | O valor da fatura de todas as transações cobertas por um item. |
| WartoscStatystyczna | O valor estatístico. |
| Wypelniajacy: NazwiskoImie, Telefon, Faks, Email | O nome e sobrenomes, número de telefone, número de fax e endereço de email da pessoa que envia a declaração. |
| IdKontrahenta | O número de IVA estrangeiro do cliente em um estado-membro da UE. |


## <a name="set-up-intrastat"></a>Configurar Intrastat

No repositório Global, você pode importar a versão mais recente das seguintes configurações de Relatório eletrônico (ER):

   - Módulo intrastat
   - Relatório intrastat
   - Intrastat (PL)

Para obter mais informações, consulte [Baixar configurações ER do repositório global de serviço de configuração](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

## <a name="set-up-a-vat-id-and-an-enterprise-number-for-your-company"></a>Configurar uma ID de IVA e um número de empresa para a sua empresa

### <a name="create-registration-types-for-company-codes"></a>Criar tipos de registro para códigos da empresa

Você deve criar dois tipos de registro para códigos da empresa: um para a ID do IVA (código de NIP) e um para o número da empresa (código de Regon).

1. Vá para **Administração da organização** > **Catálogo de endereços global** > **Tipos de registro** > **Tipos de registros**.
2. No Painel de Ações, selecione **Novo** para criar um tipo de registro para o ID do IVA.
3. Na caixa de diálogo **Inserir detalhes do tipo de registro**, no campo **Nome**, insira um nome para o novo tipo de registro. Por exemplo, insira **NIP**.
4. No campo **País/região**, selecione **POL**.
5. Selecione **Criar**.
6. No Painel de Ações, selecione **Novo** para criar um tipo de registro para o número de empresa.
7. Na caixa de diálogo **Inserir detalhes do tipo de registro**, no campo **Nome**, insira um nome para o novo tipo de registro. Por exemplo, insira **Regon**.
8. No campo **País/região**, selecione **POL**.
9. Selecione **Criar**.

### <a name="match-the-registration-types-with-registration-categories"></a>Coincida os tipos de registro com categorias de registro

1. Vá para **Administração da organização** > **Catálogo de endereços global** > **Tipos de registro** > **Categorias de registro**.
2. No Painel de Ações, selecione **Novo** para criar um link entre cada tipo de registro criado e uma categoria de registro.

    - Para o tipo de registro para a ID de IVA (código de NIP), selecione a categoria de registro **ID de IVA**.
    - Para o tipo de registro para o número de empresa (código Regon), selecione a categoria de registro **ID da Empresa (COID)**.

### <a name="set-up-a-vat-id-and-an-enterprise-number-for-your-company"></a>Configurar uma ID de IVA e um número de empresa para a sua empresa

1. Acesse **Administração da organização** > **Organizações** > **Entidades legais**.
2. Na grade, selecione sua empresa.
3. No Painel de Ações, selecione **IDs de Registro**.
4. Na Guia Rápida **ID de Registro**, selecione **Adicionar**.
5. No campo **Tipo de registro**, selecione um dos tipos de registros criados anteriormente.
6. Insira a ID de IVA da sua empresa (código de NIP) ou o número da empresa (código de Regon), dependendo do tipo de registro selecionado na etapa anterior.
7. Repita as etapas 4 a 6 para o outro tipo de registro criado anteriormente.

## <a name="set-up-a-company-address"></a>Configurar um endereço da empresa

1. Acesse **Administração da organização** > **Organizações** > **Entidades legais**.
2. Na grade, selecione sua empresa.
3. Na guia **Endereços**, selecione **Editar**.
4. Na caixa de diálogo **Editar endereço**, no campo **CEP/código postal**, selecione o CEP/código postal da sua empresa.
5. No campo **Rua**, insira seu endereço.
6. No campo **Cidade**, selecione sua cidade.

## <a name="set-up-foreign-trade-parameters"></a>Configurar parâmetros de comércio exterior

1. Vá para **Imposto** > **Configuração** > **Parâmetros de comércio exterior**.
2. Na guia **Intrastat**, na Guia Rápida **Relatório eletrônico**, no campo **Mapeamento de formato de arquivo**, selecione **Intrastat (PL)**.
3. No campo **Mapeamento de formato de relatório**, selecione **Relatório Intrastat**.
4. Na Guia Rápida **Hierarquia de código de mercadoria**, no campo **Hierarquia de categoria**, selecione **Intrastat**.
5. No campo **Código da transação**, selecione o código da transação para transferências de propriedades. Você usa esse código para transações que produzem transferências reais ou planejadas da propriedade sobre compensação (financeira ou outra). Ele também é usado para correções. As empresas na Polônia usam códigos de transação de dois dígitos.
6. No campo **Nota de crédito**, selecione o código de transação para a devolução de bens.
7. Na guia **Propriedades de país/região**, no campo **País/região**, indique todos os países ou regiões com os quais sua empresa faz negócios. Para cada país que faz parte da UE, selecione **UE** no campo **Tipo de país/região**, para que o país apareça no seu relatório Intrastat. Para Polônia, selecione **Doméstico** no campo **Tipo de país/região**.
8. Na guia **Agente**, na Guia Rápida **Agente**, na seção **Impostos**, no campo **Número de isenção de imposto**, insira **420000** para indicar o código de unidade ao qual a declaração Intrastat está endereçada.
9. Na guia **Contato**, insira o nome, número de telefone, número de fax e endereço de email da pessoa que está enviando a declaração.
10. Na guia **Sequências numéricas**, no campo **Código de sequência numérica** da referência **Número do arquivo XML**, especifique uma sequência numérica não contínua que tem, no máximo, nove caracteres. Este campo é usado para gerar automaticamente um valor para o campo **Identificador de declaração** no relatório Intrastat.

## <a name="set-up-product-parameters-for-the-intrastat-declaration"></a>Configurar os parâmetros de produto para a declaração Intrastat

1. Acesse **Gerenciamento de informações do produto** > **Produtos** > **Produtos liberados**.
2. Na grade, selecione um produto.
3. Na Guia Rápida **Comércio exterior**, na seção **Intrastat**, no campo **Mercadoria**, selecione o código da mercadoria. O nome da mercadoria será impresso no campo **Descrição de mercadorias** no relatório Intrastat.
4. Na seção **Origem**, no campo **País/região**, selecione o país ou a região de origem do produto.
5. Na Guia Rápida **Gerenciar estoque**, no campo **Peso líquido**, informe o peso do produto em quilogramas.

## <a name="set-up-compression-of-intrastat"></a>Configurar compactação do Intrastat

-   Acesse **Imposto** > **Configuração** > **Comércio exterior** > **Compactação do Intrastat** e selecione os campos que podem ser comparados quando a informação do Intrastat é resumida. Para Intrastat polonês, selecione os seguintes campos:

    - Mercadoria
    - Código de transação
    - País/região de origem
    - Transporte
    - Condições de entrega
    - País/região do remetente
    - País/região
    - Correção
    - Número de isenção de imposto
    - Direção
    - Fatura

## <a name="set-up-the-transport-method-and-delivery-terms"></a>Configurar o método de transporte e as condições de entrega

1.  Configurar códigos de transporte.

    1. Vá para **Imposto** > **Configuração** > **Comércio exterior** > **Método de transporte**.
    2. No Painel de Ações, selecione **Novo**.
    3. No campo **Transporte**, informe um código exclusivo. As empresas polonesas usam códigos de transporte de um dígito.

2.  Configurar o modo de códigos Intrastat de entrega.

    1. Vá para **Compras e fornecimento** > **Configuração** > **Distribuição** > **Condições de entrega**.
    2. Na grade, selecione um conjunto de termos de entrega.
    3. Na Guia Rápida **Geral**, no campo **Código Intrastat**, informe o código exclusivo.

## <a name="intrastat-transfer"></a>Transferência Intrastat

Na página **Intrastat**, no Painel de Ações, você pode selecionar **Transferir** para transferir automaticamente as informações sobre o comércio intracomunidade de ordens de venda, faturas de texto livre, ordens de compra, faturas de fornecedor, recebimentos de produtos do fornecedor, faturas de projeto e ordens de transferência. Somente os documentos que tiverem um país da UE como o país ou a região de destino ou consignação serão transferidos.

Você também pode inserir transações manualmente selecionando **Novo** no Painel de Ações.

### <a name="generate-an-intrastat-report"></a>Gerar um relatório do Intrastat

1. Acesse **Imposto** > **Declarações** > **Comércio exterior** > **Intrastat**.
2. No Painel de Ações, selecione **Exportar** &gt; **Relatório**.
3. Na caixa de diálogo **Relatório do Intrastat**, defina estes campos.

    | Campo | Descrição |
    |-------------------------|-------------------------|
    | Data Inicial | Selecione a data de início do relatório. |
    | Gerar arquivo | Defina esta opção como **Sim** para gerar um arquivo .xml para seu relatório Intrastat. |
    | Nome do arquivo | Insira o nome do arquivo .xml. |
    | Gerar relatório | Defina esta opção como **Sim** para gerar um arquivo .xlsx para seu relatório Intrastat. |
    | Nome do arquivo de relatório | Insira o nome do arquivo .xlsx. |
    | Direção | Selecione **Entradas** para um relatório sobre as entradas de intracomunidade.</br>Selecione **Expedições** para um relatório sobre expedições de intracomunidade. |
    | Identificador da declaração | A ID do documento é gerada automaticamente e pode ser atualizada. |
    | Tipo de declaração | Selecione **Declaração** para obter uma declaração original.</br>Selecione **Correção de declaração de seleção – substituição** para uma declaração de correção destinada a substituir completamente uma declaração original ou de correção enviada anteriormente existente. |
    | Cidade da criação de documentos | Insira o valor que deve ser impresso no campo **Miejscowosc** na declaração Intrastat. |
    | Data da criação do documento | Insira o valor que deve ser impresso no campo **Deklaracja Data** na declaração Intrastat. |
    | Nº do Documento | Insira o valor que deve ser impresso no campo **Numer** na declaração Intrastat. |
    | Versão do documento | Insira o valor que deve ser impresso no campo **Wersja** na declaração Intrastat. |

4. Selecione **OK** e revise os relatórios gerados.

## <a name="example"></a>Exemplo

Este exemplo mostra como lançar entradas e expedições para o Intrastat usando a entidade legal **DEMF**.

### <a name="preliminary-setup"></a>Configuração preliminar

Importe a versão mais recente das seguintes configurações de relatório eletrônico (ER):

   - Módulo intrastat
   - Relatório intrastat
   - Intrastat (PL)

### <a name="set-up-a-company-address"></a>Configurar um endereço da empresa

1. Acesse **Administração da organização** > **Catálogo de endereços global** > **Endereços** > **Catálogos de endereços**.
2. Na guia **Cidade**, selecione **Novo**.
3. No campo **País/região**, selecione **POL**.
4. No campo **Cidade**, insira **Warsaw**.
5. Na guia **CEP/código postal**, selecione **Novo**.
6. No campo **País/região**, selecione **POL**.
7. No campo **Cidade**, selecione **Varsóvia**.
8. No campo **CEP/código postal**, insira **00-844**.
9. Vá para **Administração da organização** > **Organização** > **Entidades legal** e selecione a entidade legal **DEMF**.
10. Na Guia Rápida **Endereços**, selecione **Editar**.
11. No campo **País/região**, selecione **POL**.
12. No campo **CEP/código postal**, selecione **31-111**.
13. No campo **Rua**, insira **Statystyczna 22/1**.
14. No campo **Cidade**, selecione **Varsóvia**.
15. Selecione **OK**.

## <a name="set-up-a-vat-id-and-an-enterprise-number-code-for-your-company"></a>Configurar uma ID de IVA e um código numérico da empresa para a sua empresa

### <a name="create-registration-types-for-company-codes"></a>Criar tipos de registro para códigos da empresa

1. Vá para **Administração da organização** > **Catálogo de endereços global** > **Tipos de registro** > **Tipos de registros**.
2. No Painel de Ações, selecione **Novo** para criar um tipo de registro para o ID do IVA (código NIP).
3. Na caixa de diálogo **Inserir detalhes do tipo de registro**, no campo **Nome**, digite **NIP**.
4. No campo **País/região**, selecione **POL**.
5. Selecione **Criar**.
6. No Painel de Ações, selecione **Novo** para criar um tipo de registro para o número de empresa (Código de Regon).
7. Na caixa de diálogo **Inserir detalhes do tipo de registro**, no campo **Nome**, digite **Regon**.
8. No campo **País/região**, selecione **POL**.
9. Selecione **Criar**.

### <a name="match-the-registration-types-with-registration-categories"></a>Coincida os tipos de registro com categorias de registro

1. Vá para **Administração da organização** > **Catálogo de endereços global** > **Tipos de registro** > **Categorias de registro**.
2. No Painel de Ações, selecione **Novo** para criar um link entre cada tipo de registro criado e uma categoria de registro.

    - Para o tipo de registro **NIP**, selecione a categoria de registro **ID de IVA**.
    - Para o tipo de registro **Regon**, selecione a categoria de registro **ID da empresa (COID)**.

### <a name="set-up-a-vat-id-and-an-enterprise-number-for-your-company"></a>Configurar uma ID de IVA e um número de empresa para a sua empresa

1. Acesse **Administração da organização** > **Organizações** > **Entidades legais**.
2. Na grade, selecione **DEMF**.
3. No Painel de Ações, selecione **IDs de Registro**.
4. Na Guia Rápida **ID de Registro**, selecione **Adicionar**.
5. No campo **Tipo de registro**, selecione **NIP**.
6. No campo **Número de registro**, insira **1234567890**.
7. Selecione **Adicionar**.
8. No campo **Tipo de registro**, selecione **Regon**.
9. No campo **Número de registro**, insira **12345678901234**.

### <a name="set-up-a-number-sequence-code"></a>Configurar código de sequências numéricas

1. Vá para **Administração da organização** > **Sequências numéricas** > **Sequências numéricas**.
2. No Painel de Ações, na guia **Sequência numérica**, no grupo **Novo**, selecione **Sequência numérica**.
3. Na Guia Rápida **Identificação**, no campo **Código de sequência numérica**, insira o **arquivo\_XML**.
4. Na Guia Rápida **Parâmetros do escopo**, no campo **Escopo**, selecione **Empresa**.
5. No campo **Empresa**, selecione **DEMF**.
6. Na Guia Rápida **Segmentos**, no campo **Duração** do segmento **Alfanumérico** digite **4**.
7. Na Guia Rápida **Geral**, na seção **Configuração**, defina a opção **Contínua** como **Não**.
8. Na seção **Alocação de números**, no campo **Maior**, digite **9999**.

### <a name="set-up-foreign-trade-parameters"></a>Configurar parâmetros de comércio exterior

1. Acesse **Imposto** > **Configuração** > **Comércio exterior** > **Parâmetros de comércio exterior**.
2. Na guia **Intrastat**, na Guia Rápida **Geral**, no campo **Código** **de transação**, selecione **11**.
3. Na Guia Rápida **Relatório eletrônico**, no campo **Mapeamento de formato de arquivo**, selecione **Intrastat (PL)**.
4. No campo **Mapeamento de formato de relatório**, selecione **Relatório Intrastat**.
5. Na Guia Rápida **Hierarquia de código de mercadoria**, verifique se o campo **Hierarquia de categoria** está definido como **Intrastat**.
6. Na guia **Propriedades de país/região**, selecione **Novo**.
7. No campo **País/região do participante**, selecione **POL**. Em seguida, no campo **Tipo de país/região**, selecione **Doméstico**.
8. No campo **País/região do participante**, selecione **DEU**. Em seguida, no campo **Tipo de país/região**, selecione **UE**.
9. Na guia **Agente**, na Guia Rápida **Agente**, na seção **Impostos**, no campo **Número de isenção de imposto**, digite **420000**.
10. Na guia **Contato**, no campo **Nome**, insira **Manish Chopra**.
11. No campo **Telefone**, insira **425-555-5068**.
12. No campo **Número de fax**, insira **425-555-5049**.
13. No campo **Email**, insira **manishc@contoso.com**.
14. Na guia **Sequências numéricas**, no campo **Código de sequência numérica** para a referência **Número do arquivo XML**, selecione **arquivo\_XML**.

### <a name="set-up-product-information"></a>Configurar informações do produto

1. Vá até **Gerenciamento de informações do produto** > **Produtos** > **Produtos** **liberados**.
2. Na grade, selecione **D0001**.
3. Na Guia Rápida **Comércio exterior**, na seção **Intrastat**, no campo **Mercadoria**, selecione **100 200 30**.
4. Na Guia Rápida **Gerenciar estoque**, na seção **Medidas de peso**, no campo **Peso líquido**, digite **2**.
5. No Painel de ações, selecione **Salvar**.
6. Na grade, selecione **D0003**.
7. Na Guia Rápida **Comércio exterior**, na seção **Intrastat**, no campo **Mercadoria**, selecione **100 200 30**.
8. Na seção **Origem**, no campo **País/região**, selecione **DEU**.
9. Na Guia Rápida **Gerenciar estoque**, na seção **Medidas de peso**, no campo **Peso líquido**, digite **5**.
10. No Painel de ações, selecione **Salvar**.

### <a name="change-the-site-address"></a>Altere o endereço do site

1. Vá para **Gerenciamento de depósito** > **Configuração** > **Configuração** > **Locais**.
2. Na grade, selecione **1**.
3. Na Guia Rápida **Endereços**, selecione **Editar**.
4. Na caixa de diálogo **Editar endereço**, no campo **País/região**, selecione **POL**.
5. Selecione **OK**.

### <a name="set-up-a-transport-method"></a>Configurar um método de transporte

1. Criar um método de transporte.

    1. Vá para **Imposto** > **Configuração** > **Comércio exterior** > **Método de transporte**.
    2. No Painel de Ações, selecione **Novo**.
    3. No campo **Transporte**, digite **3**.
    4. No campo **Descrição**, insira **Transporte rodoviário**.

2. Atribua o novo método de transporte a um modo de entrega. Dessa forma, você configura os valores padrão usados para o método de transporte quando o modo de entrega correspondente for selecionado.

    1. Acesse **Compras e fornecimento** > **Configuração** > **Distribuição** > **Modos de entrega**.
    2. Na grade, selecione **10**.
    3. Na Guia Rápida **Comércio exterior**, no campo **Transporte**, selecione **3**.

3. Selecione o modo padrão de entrega para um cliente.

    1. Vá para **Contas a receber** > **Clientes** > **Todos os clientes**.
    2. Na grade, selecione **DE-016**.
    3. Na Guia Rápida **Fatura e entrega**, no campo **Modo de entrega**, selecione **10**.

4. Selecione o modo padrão de entrega para um fornecedor.

    1. Vá para **Contas a pagar** > **Fornecedores** > **Todos os fornecedores**.
    2. Na grade, selecione **DE-001**.
    3. Na Guia Rápida **Fatura e entrega**, no campo **Modo de entrega**, selecione **10**.

### <a name="set-up-codes-for-terms-of-delivery"></a>Configurar códigos para condições de entrega

1. Configurar um código Intrastat para as condições de entrega.

    1. Vá para **Compras e fornecimento** > **Configuração** > **Distribuição** > **Condições de entrega**.
    2. Na grade, selecione **CIF**.
    3. Na Guia Rápida **Geral**, no campo **Código Intrastat**, digite **CIF**.

2. Selecione as condições de entrega padrão para um cliente.

    1. Vá para **Contas a receber** > **Clientes** > **Todos os clientes**.
    2. Na grade, selecione **DE-016**.
    3. Na Guia Rápida **Fatura e entrega**, no campo **Condições de entrega**, selecione **CIF**.

3. Selecione as condições de entrega padrão para um fornecedor.

    1. Vá para **Contas a pagar** > **Fornecedores** > **Todos os fornecedores**.
    2. Na grade, selecione **DE-001**.
    3. Na Guia Rápida **Fatura e entrega**, no campo **Condições de entrega**, selecione **CIF**.

### <a name="verify-an-eu-customers-tax-exempt-number-code"></a>Verifique um código do número de isenção de imposto do cliente da UE

1. Vá para **Contas a receber** > **Clientes** > **Todos os clientes**.
2. Na grade, selecione **DE-016**.
3. Na Guia Rápida **Fatura e entrega**, na seção **Impostos**, verifique se o campo **Número de isenção de impostos** está definido como **DE9012**.

### <a name="create-a-sales-order-with-an-eu-customer"></a>Crie uma ordem de venda com um cliente da UE

1. Acesse **Contas a receber** > **Ordens** > **Todas as ordens de venda**.
2. No Painel de Ações, selecione **Novo**.
3. Na caixa de diálogo **Criar ordem de venda**, na Guia Rápida **Cliente**, na seção **Cliente**, no campo **Conta do cliente**, selecione **DE-016**.
4. Na Guia Rápida **Geral**, na seção **Dimensões de armazenamento**, no campo **Site**, selecione **1**.
5. No campo **Depósito**, selecione **11**.
6. Na guia **Endereço**, verifique se o campo **Endereço** está definido como **Teichgasse 12, Kiel, 24103, DEU**, porque o cliente é da Alemanha.
7. Selecione **OK**.
8. Na guia **Cabeçalho**, na Guia Rápida **Entrega**, verifique se o campo **Condições de entrega** foi definido como **CIF** e o campo **Modo de entrega** foi definido como **10**.
9. Na guia **Linhas**, na Guia Rápida **Linhas de ordem de venda**, no campo **Número do item**, selecione **D0001**. Depois, no campo **Quantidade**, insira **8**.
10. Na Guia Rápida **Detalhes da linha**, na guia **Comércio exterior**, verifique se o campo **Código da transação** está definido como **11**, o campo **Mercadoria** está definido como **100 200 30** e o campo **País/região de origem** está definido como **POL**.
11. No Painel de ações, selecione **Salvar**.
12. No Painel de Ação, na guia **Fatura**, no grupo **Gerar**, selecione **Fatura**.
13. Na caixa de diálogo **Lançando fatura**, na Guia Rápida **Parâmetros**, na seção **Parâmetro**, no campo **Quantidade**, selecione **Tudo**.
14. Na Guia Rápida **Configurar**, no campo **Data de venda**, selecione **10/18/2021** (18 de Outubro, 2021).
15. Selecione **OK** para lançar a fatura.

### <a name="transfer-the-transaction-to-the-intrastat-journal-and-review-the-result"></a>Transfira a transação para o diário Intrastat e revise o resultado

1. Acesse **Imposto** > **Declarações** > **Comércio exterior** > **Intrastat**.
2. No Painel de Ação, selecione **Transferir**.
3. Na caixa de diálogo **Intrastat (Transferência)**, na seção **Parâmetros**, defina a opção **Fatura de cliente** como **Sim**.
4. Selecione **Filtro**.
5. Na caixa de diálogo **Filtro Intrastat**, na guia **Intervalo**, selecione a primeira linha e verifique se o campo **Campo** está definido como **Data**.
6. No campo **Critérios**, selecione a data atual.
7. Selecione **OK** para fechar a caixa de diálogo **Filtro Intrastat**.
8. Selecione **OK** para fechar a caixa de diálogo **Intrastat (Transferência)** e revisar o resultado. A linha representa a ordem de venda que você criou anteriormente.

    ![Linha que representa a ordem de venda na página Intrastat](media/intrastat_pl_1.png)

9. Selecione a linha de transação e, em seguida, a guia **Geral** para exibir mais detalhes.

    ![Detalhes da ordem de venda na guia Geral da página Intrastat](media/intrastat_pl_2.png)

10. No Painel de Ações, selecione **Saída** > **Relatório**.
11. Na caixa de diálogo **Relatório Intrastat**, na Guia Rápida **Parâmetros**, na seção **Data**, no campo **Data inicial**, selecione o primeiro dia do mês atual.
12. Na seção **Opções** **de exportação**, defina a opção **Gerar arquivo** como **Sim**. Em seguida, no campo **Nome do arquivo**, insira o nome necessário.
13. Defina a opção **Gerar relatório** como **Sim**. Em seguida, no campo **Nome do arquivo do relatório**, insira o nome necessário.
14. No campo **Direção**, selecione **Expedições**.
15. Na seção **Mapeamento de formato de arquivo**, verifique se o campo **Tipo de declaração** está definido como **Declaração**.
16. No campo **Cidade de criação do documento**, insira **Krakow**.
17. No campo **Data de criação de documento**, selecione **19/10/2021** (19 de outubro, 2021).
18. No campo **Nº do Documento**, digite **11**.
19. No campo **Versão do documento**, digite **22**.
20. Selecione **OK** e revise o relatório no formato XML que foi gerado. A tabela a seguir mostra os valores no relatório de exemplo.

    <table>
    <tbody>
    <tr>
    <td>
    <p><strong>Nome do campo</strong></p>
    </td>
    <td>
    <p><strong>Descrição do campo</strong></p>
    </td>
    <td>
    <p><strong>Alíquota</strong></p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>Informações sobre o documento</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Deklaracja Data</p>
    </td>
    <td>
    <p>A data em que o documento foi criado.</p>
    </td>
    <td>
    <p>19-10-2021</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Miejscowosc</p>
    </td>
    <td>
    <p>A cidade na qual o documento foi criado.</p>
    </td>
    <td>
    <p>Krakow</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaLiczbaPozycji</p>
    </td>
    <td>
    <p>O número total de itens.</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaWartoscStatystyczna</p>
    </td>
    <td>
    <p>O valor total estatístico.</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaWartoscFaktur</p>
    </td>
    <td>
    <p>O valor total da fatura.</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>UC</p>
    </td>
    <td>
    <p>O código de unidade.</p>
    </td>
    <td>
    <p>420000</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Rodzaj</p>
    </td>
    <td>
    <p>O tipo da declaração.</p>
    </td>
    <td>
    <p>B</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Wersja</p>
    </td>
    <td>
    <p>A versão do documento.</p>
    </td>
    <td>
    <p>22</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Numer</p>
    </td>
    <td>
    <p>O número do documento.</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Miesiac</p>
    </td>
    <td width="330">
    <p>O mês de referência.</p>
    </td>
    <td>
    <p>10</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Rok</p>
    </td>
    <td width="330">
    <p>O ano de referência.</p>
    </td>
    <td>
    <p>2021</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Typ</p>
    </td>
    <td width="330">
    <p>A direção do relatório.</p>
    </td>
    <td>
    <p>Q</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>NrWlasny</p>
    </td>
    <td width="330">
    <p>O identificador da declaração.</p>
    </td>
    <td>
    <p>21ISTDEMF-0001</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>Informações sobre a empresa</strong></p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Miejscowosc</p>
    </td>
    <td width="330">
    <p>A cidade na qual a empresa está localizada.</p>
    </td>
    <td>
    <p>Varsóvia</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Regon</p>
    </td>
    <td width="330">
    <p>O código Regon da empresa.</p>
    </td>
    <td>
    <p>12345678901234</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Nip</p>
    </td>
    <td>
    <p>O código NIP da empresa.</p>
    </td>
    <td>
    <p>1234567890</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KodPocztowy</p>
    </td>
    <td>
    <p>O CEP/código postal da empresa.</p>
    </td>
    <td>
    <p>31-111</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>UlicaNumer</p>
    </td>
    <td>
    <p>A rua na qual a empresa está localizada.</p>
    </td>
    <td>
    <p>Statystyczna 22/1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Nazwa</p>
    </td>
    <td>
    <p>O nome da empresa.</p>
    </td>
    <td>
    <p>Contoso Entertainment System Germany</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>Informações sobre a mercadoria</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WartoscStatystyczna</p>
    </td>
    <td>
    <p>O valor estatístico.</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WartoscFaktury</p>
    </td>
    <td>
    <p>O valor da fatura.</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>MasaNetto</p>
    </td>
    <td>
    <p>A massa líquida.</p>
    </td>
    <td>
    <p>16</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>IdKontrahenta</p>
    </td>
    <td>
    <p>O número de IVA do cliente.</p>
    </td>
    <td>
    <p>DE9012</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KodTowarowy</p>
    </td>
    <td>
    <p>O código da mercadoria.</p>
    </td>
    <td>
    <p>10020030</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>RodzajTransakcji</p>
    </td>
    <td>
    <p>O código da transação.</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WarunkiDostawy</p>
    </td>
    <td>
    <p>As condições do modo de entrega.</p>
    </td>
    <td>
    <p>CIF</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KrajPochodzeniaWysylki</p>
    </td>
    <td>
    <p>O código do país ou da região de despacho/destino.</p>
    </td>
    <td>
    <p>DE</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>OpisTowaru</p>
    </td>
    <td>
    <p>Uma descrição das mercadorias.</p>
    </td>
    <td>
    <p>Hardware</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>PozId</p>
    </td>
    <td>
    <p>O número do item.</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>Informações do contato</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Email</p>
    </td>
    <td>
    <p>O endereço de email do locatário do emissor.</p>
    </td>
    <td>
    <p>manishc@contoso.com</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Faks</p>
    </td>
    <td>
    <p>O número do fax do emissor.</p>
    </td>
    <td>
    <p>425-555-5049</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Telefon</p>
    </td>
    <td>
    <p>O número de telefone do emissor.</p>
    </td>
    <td>
    <p>425-555-5068</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>NazwiskoImie</p>
    </td>
    <td>
    <p>O nome do emissor.</p>
    </td>
    <td>
    <p>Manish Chopra</p>
    </td>
    </tr>
    </tbody>
    </table>

21. Revise o relatório no formato do Excel que foi gerado.

    ![Relatório intrastat sobre expedições](media/intrastat_pl_3.png)

### <a name="create-a-purchase-order"></a>Crie uma ordem de compra

1. Vá para **Contas a pagar** > **Ordens de compra** > **Todas as ordens de compra**.
2. No Painel de Ações, selecione **Novo**.
3. Na caixa de diálogo **Criar ordem de venda**, no campo **Conta do fornecedor**, selecione **DE-001**.
4. No campo **Local**, selecione **1**.
5. No campo **Depósito**, selecione **11**.
6. Selecione **OK**.
7. Na guia **Cabeçalho**, na Guia Rápida **Entrega**, verifique se o campo **Modo de entrega** foi definido como **10** e o campo **Condições de entrega** foi definido como **CIF**.
8. Na guia **Linhas**, na Guia Rápida **Linhas de ordem de compra**, no campo **Número do item**, selecione **D0003**. Depois, no campo **Quantidade**, insira **6**.
9. Na Guia Rápida **Detalhes da linha**, na guia **Comércio exterior**, verifique se o **Código da transação** está definido como **11**, o campo **Transporte** está definido como **3**, o campo **Mercadoria** está definido como **100 200 30** e o campo **País/região de origem** está definido como **DEU**.
10. No Painel de Ação, na guia **Compra**, no grupo **Ações**, selecione **Confirmar**.
11. No Painel de Ação, na guia **Fatura**, no grupo **Gerar**, selecione **Fatura**.
12. No Painel de Ações, selecione **Padrão de** e no campo **Quantidade padrão para linhas**, selecione **Quantidade solicitada**. Em seguida, selecione **OK**.
13. Na Guia Rápida **Cabeçalho da fatura de fornecedor**, na seção **Identificação da fatura**, no campo **Número**, digite **00010**.
14. Na seção **Datas da fatura**, no campo **Data da fatura**, selecione a data atual. Essa data será usada para a transferência Intrastat.
15. No campo **Data de recebimento do documento**, selecione **18/10/2021** (18 de outubro, 2021).
16. No Painel de Ações, selecione **Lançar** para lançar a fatura.

### <a name="create-an-intrastat-declaration-for-arrivals"></a>Criar uma declaração Intrastat para entradas

1. Acesse **Imposto** > **Declarações** > **Comércio exterior** > **Intrastat**.
2. No Painel de Ação, selecione **Transferir**.
3. Na caixa de diálogo **Intrastat (Transferência)**, defina a opção **Fatura do fornecedor** como **Sim**.
4. Selecione **OK** para transferir as transações e depois revise o diário Intrastat.

    ![Linha que representa a ordem de compra na página Intrastat](media/intrastat_pl_4.png)

5. Revise as informações na guia **Geral** da ordem de compra.

    ![Detalhes da ordem de compra na guia Geral da página Intrastat](media/intrastat_pl_5.png)

6. No Painel de Ações, selecione **Saída** > **Relatório**.
7. Na caixa de diálogo **Relatório Intrastat**, na Guia Rápida **Parâmetros**, na seção **Data**, no campo **Data inicial**, selecione o primeiro dia do mês atual.
8. Na seção **Opções** **de exportação**, defina a opção **Gerar arquivo** como **Sim**. Em seguida, no campo **Nome do arquivo**, insira o nome necessário.
9. Defina a opção **Gerar relatório** como **Sim**. Em seguida, no campo **Nome do arquivo do relatório**, insira o nome necessário.
10. No campo **Direção**, selecione **Entradas**.
11. Na seção **Mapeamento de formato de arquivo**, verifique se o campo **Tipo de declaração** está definido como **Declaração**.
12. No campo **Cidade de criação do documento**, insira **Krakow**.
13. No campo **Data de criação de documento**, selecione **19/10/2021** (19 de outubro, 2021).
14. No campo **Nº do Documento**, digite **11**.
15. No campo **Versão do documento**, digite **22**.
16. Selecione **OK** e revise o relatório no formato XML que foi gerado. A tabela a seguir mostra os valores no relatório de exemplo.

    <table>
    <tbody>
    <tr>
    <td>
    <p><strong>Nome do campo</strong></p>
    </td>
    <td>
    <p><strong>Descrição do campo</strong></p>
    </td>
    <td>
    <p><strong>Alíquota</strong></p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p style="text-align: center;"><strong>Informações sobre o documento</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Deklaracja Data</p>
    </td>
    <td>
    <p>A data em que o documento foi criado.</p>
    </td>
    <td>
    <p>19-10-2021</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Miejscowosc</p>
    </td>
    <td>
    <p>A cidade na qual o documento foi criado.</p>
    </td>
    <td>
    <p>Krakow</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaLiczbaPozycji</p>
    </td>
    <td>
    <p>O número total de itens.</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaWartoscStatystyczna</p>
    </td>
    <td>
    <p>O valor total estatístico.</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>LacznaWartoscFaktur</p>
    </td>
    <td>
    <p>O valor total da fatura.</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>UC</p>
    </td>
    <td>
    <p>O código de unidade.</p>
    </td>
    <td>
    <p>420000</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Rodzaj</p>
    </td>
    <td>
    <p>O tipo da declaração.</p>
    </td>
    <td>
    <p>B</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Wersja</p>
    </td>
    <td>
    <p>A versão do documento.</p>
    </td>
    <td>
    <p>22</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Numer</p>
    </td>
    <td>
    <p>O número do documento.</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Miesiac</p>
    </td>
    <td width="332">
    <p>O mês de referência.</p>
    </td>
    <td>
    <p>10</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Rok</p>
    </td>
    <td width="332">
    <p>O ano de referência.</p>
    </td>
    <td>
    <p>2021</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Typ</p>
    </td>
    <td width="332">
    <p>A direção do relatório.</p>
    </td>
    <td>
    <p>S</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>NrWlasny</p>
    </td>
    <td width="332">
    <p>O identificador da declaração.</p>
    </td>
    <td>
    <p>21ISTDEMF-0002</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p style="text-align: center;"><strong>Informações sobre a empresa</strong></p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Miejscowosc</p>
    </td>
    <td width="332">
    <p>A cidade na qual a empresa está localizada.</p>
    </td>
    <td>
    <p>Varsóvia</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Regon</p>
    </td>
    <td width="332">
    <p>O código Regon da empresa.</p>
    </td>
    <td>
    <p>12345678901234</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Nip</p>
    </td>
    <td>
    <p>O código NIP da empresa.</p>
    </td>
    <td>
    <p>1234567890</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KodPocztowy</p>
    </td>
    <td>
    <p>O CEP/código postal da empresa.</p>
    </td>
    <td>
    <p>31-111</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>UlicaNumer</p>
    </td>
    <td>
    <p>A rua na qual a empresa está localizada.</p>
    </td>
    <td>
    <p>Statystyczna 22/1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Nazwa</p>
    </td>
    <td>
    <p>O nome da empresa.</p>
    </td>
    <td>
    <p>Contoso Entertainment System Germany</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p style="text-align: center;"><strong>Informações sobre a mercadoria</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WartoscStatystyczna</p>
    </td>
    <td>
    <p>O valor estatístico.</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WartoscFaktury</p>
    </td>
    <td>
    <p>O valor da fatura.</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>MasaNetto</p>
    </td>
    <td>
    <p>A massa líquida.</p>
    </td>
    <td>
    <p>30</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KrajPochodzenia</p>
    </td>
    <td>
    <p>O código do país ou da região de origem.</p>
    </td>
    <td>
    <p>DE</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>RodzajTransportu</p>
    </td>
    <td>
    <p>O código do modo de transporte.</p>
    </td>
    <td>
    <p>3</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KodTowarowy</p>
    </td>
    <td>
    <p>O código da mercadoria.</p>
    </td>
    <td>
    <p>10020030</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>RodzajTransakcji</p>
    </td>
    <td>
    <p>O código da transação.</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WarunkiDostawy</p>
    </td>
    <td>
    <p>As condições do modo de entrega.</p>
    </td>
    <td>
    <p>CIF</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>KrajPochodzeniaWysylki</p>
    </td>
    <td>
    <p>O código do país ou da região de despacho/destino.</p>
    </td>
    <td>
    <p>DE</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>OpisTowaru</p>
    </td>
    <td>
    <p>Uma descrição das mercadorias.</p>
    </td>
    <td>
    <p>Hardware</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>PozId</p>
    </td>
    <td>
    <p>O número do item.</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p style="text-align: center;"><strong>Informações do contato</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Email</p>
    </td>
    <td>
    <p>O endereço de email do locatário do emissor.</p>
    </td>
    <td>
    <p>manishc@contoso.com</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Faks</p>
    </td>
    <td>
    <p>O número do fax do emissor.</p>
    </td>
    <td>
    <p>425-555-5049</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Telefon</p>
    </td>
    <td>
    <p>O número de telefone do emissor.</p>
    </td>
    <td>
    <p>425-555-5068</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>NazwiskoImie</p>
    </td>
    <td>
    <p>O nome do emissor.</p>
    </td>
    <td>
    <p>Manish Chopra</p>
    </td>
    </tr>
    </tbody>
    </table>

17. Revise o relatório no formato do Excel que foi gerado.

    ![Relatório Intrastat sobre entradas](media/intrastat_pl_6.png)
