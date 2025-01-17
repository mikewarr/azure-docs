---
title: What is Azure Virtual Network encryption?
titleSuffix: Azure Virtual Network
description: Learn about Azure Virtual network encryption. Virtual network encryption allows you to seamlessly encrypt and decrypt traffic between Azure Virtual Machines.
ms.service: virtual-network
author: asudbring
ms.author: allensu
ms.topic: overview
ms.date: 02/27/2024
ms.custom: template-overview, references_regions
# Customer intent: As a network administrator, I want to learn about encryption in Azure Virtual Network so that I can secure my network traffic.

---

#  What is Azure Virtual Network encryption?

Azure Virtual Network encryption is a feature of Azure Virtual Networks. Virtual network encryption allows you to seamlessly encrypt and decrypt traffic between Azure Virtual Machines. 

Whenever Azure customer traffic moves between datacenters, Microsoft applies a data-link layer encryption method using the IEEE 802.1AE MAC Security Standards (MACsec). This encryption is implemented to secure the traffic outside physical boundaries not controlled by Microsoft or on behalf of Microsoft. This method is applied from point-to-point across the underlying network hardware. Virtual network encryption enables you to encrypt traffic between Virtual Machines and Virtual Machines Scale Sets within the same virtual network. It also encrypts traffic between regionally and globally peered virtual networks. Virtual network encryption enhances existing encryption in transit capabilities in Azure.

For more information about encryption in Azure, see [Azure encryption overview](/azure/security/fundamentals/encryption-overview).

## Requirements

Virtual network encryption has the following requirements:

- Virtual Network encryption is supported on general-purpose and memory optimized VM instance sizes including:

    | Type | VM Series | VM SKU |
    | --- | --- | --- |
    | General purpose workloads | D-series V4 </br> D-series V5 | **[Dv4 and Dsv4-series](/azure/virtual-machines/dv4-dsv4-series)** </br> **[Ddv4 and Ddsv4-series](/azure/virtual-machines/ddv4-ddsv4-series)** </br> **[Dav4 and Dasv4-series](/azure/virtual-machines/dav4-dasv4-series)** </br> **[Dv5 and Dsv5-series](/azure/virtual-machines/dv5-dsv5-series)** </br> **[Ddv5 and Ddsv5-series](/azure/virtual-machines/ddv5-ddsv5-series)** </br> **[Dlsv5 and Dldsv5-series](/azure/virtual-machines/dlsv5-dldsv5-series)** </br> **[Dasv5 and Dadsv5-series](/azure/virtual-machines/dasv5-dadsv5-series)** |
    | General purpose and memory intensive workloads | E-series V4 </br> E-series V5 | **[Ev4 and Esv4-series](/azure/virtual-machines/ev4-esv4-series)** </br> **[Edv4 and Edsv4-series](/azure/virtual-machines/edv4-edsv4-series)** </br> **[Eav4 and Easv4-series](/azure/virtual-machines/eav4-easv4-series)** </br> **[Ev5 and Esv5-series](/azure/virtual-machines/ev5-esv5-series)** </br> **[Edv5 and Edsv5-series](/azure/virtual-machines/edv5-edsv5-series)** </br> **[Easv5 and Eadsv5-series](/azure/virtual-machines/easv5-eadsv5-series)** |
    | Storage intensive workloads | LSv3 | **[LSv3-series](/azure/virtual-machines/lsv3-series)**  |
    | Memory intensive workloads | M-series | **[Msv3 and Mdsv3 Medium Memory Series](/azure/virtual-machines/msv3-mdsv3-medium-series)** </br> **[Mv2-series](/azure/virtual-machines/mv2-series)** |

- Accelerated Networking must be enabled on the network interface of the virtual machine. For more information about Accelerated Networking, see  [What is Accelerated Networking?](/azure/virtual-network/accelerated-networking-overview).

- Encryption is only applied to traffic between virtual machines in a virtual network. Traffic is encrypted from a private IP address to a private IP address.

- Global Peering is supported in regions where virtual network encryption is supported.

- Traffic to unsupported Virtual Machines is unencrypted. Use Virtual Network Flow Logs to confirm flow encryption between virtual machines. For more information, see [Virtual network flow logs](../network-watcher/vnet-flow-logs-overview.md).

- The start/stop of existing virtual machines is required after enabling encryption in a virtual network.

## Availability

General Availability (GA) of Azure Virtual Network encryption is available in the following regions:

- East Asia

- East US

- East US 2

- Europe North

- Europe West

- France Central

- India Central

- Japan East

- Japan West

- UAE North

- UK South

- Swiss North

- West Central US

- West US

- West US 2

## Limitations

Azure Virtual Network encryption has the following limitations:

- In scenarios where a PaaS is involved, the virtual machine where the PaaS is hosted dictates if virtual network encryption is supported. The virtual machine must meet the listed requirements. 

- For Internal load balancer, all virtual machines behind the load balancer must be a supported virtual machine SKU. 

## Next steps

- For more information about Azure Virtual Networks, see [What is Azure Virtual Network?](/azure/virtual-network/virtual-networks-overview)


