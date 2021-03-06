---
title: Configurar o compartilhamento de dados financeiros entre empresas
description: Este procedimento mostra como configurar, habilitar, validar e resolver conflitos para compartilhar dados entre empresas.
author: aprilolson
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DataManagementWorkspace, DMFQuickImportExportRnr, DMFExecutionHistoryWorkspace, DMFExecutionHistorySummary, DMFExecutionHistoryEntities,  SysDataSharingConfiguration, SysDataSharingDiscrepencies
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 35ec8fc809841c0830224646fb57b0e4e4d40ef4
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752283"
---
# <a name="configure-financial-cross-company-data-sharing"></a>Configurar o compartilhamento de dados financeiros entre empresas

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como configurar, habilitar, validar e resolver conflitos para compartilhar dados entre empresas. A empresa usa USMF e as datas financeiras que compartilham o modelo.

Este guia de tarefas requer a plataforma 7.1 do Dynamics AX ou posterior.

1. Vá para **Painel de navegação > Módulos > Administração do sistema > Espaços de trabalho > Gerenciamento de dados**.
2. Clique em **Importar**.
3. No campo **Nome**, digite um valor.
4. No campo **Formato de dados de origem**, selecione o tipo 'Pacote'. Clique em **Carregar**. Vá para o local do Arquivo do pacote de modelo de compartilhamento de dados financeiros e selecione este arquivo.
5. Clique em **Salvar**.
6. Na lista, marque a linha selecionada. Selecione os dados que compartilham a diretiva que acabou de ser criada.  
7. Clique em **Importar**.
8. Clique em **Fechar**.
9. Atualize a página.
10. Feche a página.
11. Feche a página.
12. Feche a página.
13. Vá para **Painel de navegação > Módulos > Administração do sistema > Configuração > Configurar o compartilhamento de dados entre empresas**.
14. Na lista, localize e selecione **Dias de pagamento**.
15. Clique em **Adicionar**.
16. Na lista, marque a linha selecionada.
17. No campo **Empresa**, digite 'USSI'.
18. Clique em **Adicionar**.
19. No campo **Empresa**, digite 'USMF'.
20. Clique em **Salvar**.
21. Clique em **Habilitar**.
22. Clique em **Sim**.
23. Clique em **Localizar problemas de compartilhamento**.
24. Clique em **Sim**.
25. Clique em **Atualizar valor do campo**.
26. Clique em **Usar valor da empresa 1**.
27. Atualize a página.
28. Feche a página.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]