---
title: "Integração fiscal do canal de varejo"
description: "Este tópico oferece uma visão geral da integração fiscal do Retail POS."
author: josaw
manager: annbe
ms.date: 11/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: v-kikozl
ms.search.validFrom: 2018-11-1
ms.dyn365.ops.version: 8.1.1
ms.translationtype: HT
ms.sourcegitcommit: 0450326dce0ba6be99aede4ebc871dc58c8039ab
ms.openlocfilehash: c852d095505abecbd44d29e9e7b53875e9069def
ms.contentlocale: pt-br
ms.lasthandoff: 11/01/2018

---
# <a name="fiscal-integration-for-retail-channel"></a>Integração fiscal do canal de varejo

[!include [banner](../includes/banner.md)]

Este tópico é uma visão geral da funcionalidade de integração fiscal que está disponível no Microsoft Dynamics 365 for Retail. A funcionalidade de integração fiscal é uma estrutura criada para dar suporte às leis fiscais locais, visando evitar fraudes no setor de varejo. Os cenários típicos que podem ser cobertos usando a integração fiscal incluem:

- Impressão de um recibo fiscal e oferta ao cliente.
- Proteção do envio das informações relacionadas às vendas e às devoluções realizadas em PDV para um serviço externo oferecido pela autoridade.
- Uso da proteção de dados com uma assinatura digital autorizada pela autoridade.

Este tópico oferece diretrizes para configurar a integração fiscal para que os usuários possam executar as tarefas a seguir. 

- Configurar os conectores fiscais, que são os dispositivos ou serviços fiscais usados para fins de registro fiscal, como a salva de assinaturas digitais e o envio protegido de dados fiscais.
- Configure o provedor de documentos, que define um método de saída e um algoritmo de geração de documento fiscal.
- Configurar o processo de registro fiscal, que define uma sequência de etapas e um grupo de conectores usados em cada etapa.
- Atribuir processos de registro fiscal aos perfis de funcionalidade de PDV.
- Atribuir perfis técnicos de conector para perfis de hardware (para os conectores fiscais locais) ou para perfis de funcionalidade de PDV (para outros tipos de contector fiscal).

## <a name="fiscal-integration-execution-flow"></a>Fluxo de execução de integração fiscal
O cenário a seguir mostra o fluxo de execução de integração fiscal comum.

1. Inicialização do processo de registro fiscal.
  
   Depois de executar algumas ações onde o registro fiscal é necessário, como após uma transação de varejo ser concluída, o processo de registro fiscal é associado ao perfil atual de funcionalidade de PDV.

1. Procure um conector fiscal.
   
   Para cada etapa do registro fiscal incluída no processo de registro fiscal, o sistema coincide a lista de conectores fiscais. Esses conectores têm um perfil funcional incluído no grupo de conectores especificado, com uma lista de conectores com um perfil técnico associado ao perfil de hardware atual (de um tipo de conector que seja apenas igual a **Local**) ou com o perfil atual de funcionalidade de PDV (para outros tipos de conector).
   
1. Executar a integração fiscal.

   O sistema executa todas as ações necessárias definidas por um assembly vinculado ao conector encontrado. Isso é feito de acordo com as configurações do perfil funcional funcional e do perfil técnico que foram encontrados na etapa anterior para esse conector.

## <a name="setup-needed-before-using-fiscal-integration"></a>Configuração necessária antes de usar a integração fiscal
Antes de usar a funcionalidade de integração fiscal, você deve definir estas configurações:

- Defina a sequência numérica na página **Parâmetros de varejo** para o número de perfil funcional fiscal.
  
- Defina as sequências numéricas na página **Parâmetros compartilhados de varejo** para as seguintes referências:
  
  - Número do perfil técnico fiscal
  - Número do grupo do conector fiscal
  - Número do processo de registro

- Crie um **Conector fiscal** em **Varejo > Configuração de canal > integração fiscal > Conectores fiscais** para cada dispositivo ou serviço que você pretenda usar para fins de integração fiscal.

-  Crie um **Provedor de documento fiscal** em **Varejo > Configuração de canal > Integração fiscal > Provedores de documento fsical** para todos os conectores fiscais. O mapeamento de dados é considerado parte do provedor de documento fiscal. Para configurar diferentes mapeamentos de dados para o mesmo conector (como regulamentações específicas de estado), crie diferentes provedores de documento fiscal.

- Crie um **Perfil funcional de conector** em **Varejo > Configuração de canal > Integração fiscal > Perfis funcionais de conector** para cada fornecedor de documento fiscal.
  - Selecione um nome de conector.
  - Selecione um provedor de documento.
  - Especifique configurações de alíquota de IVA na guia **Configuração de serviço**.
  - Especifique o mapeamento de códigos IVA e o mapeamento de tipo de meio de pagamento na guia **Mapeamento de dados**.

  #### <a name="examples"></a>Exemplos 

  |  | Formatar | Exemplo | 
  |--------|--------|--------|
  | Configurações de alíquotas de IVA | valor: VATrate | 1 : 2000, 2 : 1800 |
  | Mapeamento dos códigos IVA | VATcode : valor | vat20 : 1, vat18 : 2 |
  | Mapeamento de tipos de meio de pagamento | TenderTyp: valor | Caixa: 1, cartão: 2 |

- Crie **Grupos de conectores fiscais** em **Varejo > Configuração de canal > Integração fiscal > Grupo de conectores fiscais**. Um grupo de conectores é um subconjunto de perfis funcionais vinculados a conectores fiscais que executam funções idênticas e são usados no mesmo estágio em um processo de registro fiscal.

   - Adicione perfis funcionais ao grupo de conectores. Clique em **Adicionar** na página **Perfis funcionais** e selecione um número do perfil.
   - Se desejar suspender o uso do perfil funcional, defina **Desabilitar** como **Sim**. 
   
     Esta alteração afeta apenas o grupo de conectores atual. Você pode continuar usando o mesmo perfil funcional em outros grupos de conectores.

     >[!NOTE]
     > Em um grupo de conectores, cada conector fiscal só pode ter um perfil funcional.

- Crie um **Perfil técnico do conector** em **Varejo > Configuração de canal > Integração fiscal > Perfis técnicos do conector** para cada conector fiscal.
  - Selecione um nome de conector.
  - Selecione um tipo de conector: 
      - **Local** - Configure este tipo de dispositivos físicos ou aplicativos instalados em um computador local.
      - **Interno** - Configure este tipo de dispositivos e serviços fiscais conectados ao Retail Server.
      - **Externo** - Para serviços fiscais externos como um portal da Web fornecido por uma autoridade de impostos.
    
  - Especifique configurações na guia **Conexão**.

      
 >[!NOTE]
 > Uma versão atualizada de uma configuração que foi carregada antes será carregada para perfis funcionais e técnicos. Se um conector apropriado ou provedor de documentos já estiver em uso, você será notificado. Por padrão, todas as alterações feitas manualmente em perfis funcionais e técnicos serão armazenadas. Para substituir esses perfis pelo conjunto padrão de parâmetros de uma configuração, clique em **Atualizar** na página **Perfis funcionais do conector** e na página **Perfis técnicos do conector**.
 
- Crie um **Processo de registro fiscal** em **Varejo > Configuração de canal > Integração fiscal > Processos de registros fiscais** para cada processo exclusivo da integração fiscal. Um processo de registro é definido pela sequência das etapas de registro e do grupo de conectores usados em cada etapa. 
  
  - Adicione as etapas do registro ao processo:
      - Clique em **Adicionar**.
      - Selecione um tipo de conector.
      
      >[!NOTE]
      > Este campo define onde o sistema pesquisará em um perfil técnico para o conector, em perfis de hardware para o tipo de conector **Local**ou em perfis de funcionalidade de PDV para outros tipos de conectores fiscais.
      
   - Selecione um grupo de conectores.
   
     >[!NOTE]
     > Clique em **Validar** para verificar a integridade da estrutura do processo de registro. É recomendável que validações sejam feitas nos seguintes casos:
       >- Para um novo processo de registro após todas as configurações serem concluídas, inclusive a associação de perfis de funcionalidade de PDV e perfis de hardware.
       >- Após fazer atualizações em um processo de registro existente.

-  Associe processos de registro fiscal a perfis de funcionalidade de PDV em **Varejo > Configuração de canal > Configuração do PDV > Perfis de PDV > Perfis de funcionalidade**.
   - Clique em **Editar** e selecione um **Número do processo** na guia **Processo de registro fiscal**.
- Associe os perfis técnicos de conector aos perfis de hardware em **Varejo > Configuração de canal > Configuração do PDV > Perfis de PDV > Perfis de hardware**.
   - Clique em **Editar**. Depois, clique em **Novo** na guia **Perfil técnico fiscal**.
   - Selecione um perfil técnico de conector no campo **Número do perfil**.
   
     >[!NOTE]
     > Você pode adicionar vários perfis técnicos a um perfil de hardware. Entretanto, isso não é tem suporte se um perfil de hardware tem mais de uma interseção a qualquer grupo de conectores. Para evitar configurações incorretas, é recomendável validar o processo de registro após atualizar todos os perfis de hardware.

