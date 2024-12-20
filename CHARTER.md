# RISC-V AP-TEE-IO TG Charter 

Chair: Samuel Ortiz (Rivos Inc.)
Vice-chair: Jiewen Yao (Intel)

In order to achieve high performance Input/Output (I/O) operations, Trusted Execution Environment Virtual Machines (TVM) must extend their trust boundary to include a composition of directly assigned, TEE-I/O-capable devices/functions. Without this ability, TVMs have to resort to using para-virtualized I/O using non-confidential memory regions, which has performance impacts due to memory copies and negates use of accelerators used for dense compute. This TG will define AP-TEE-IO ABI extensions to provide Confidential VM-assigned devices with secure direct access to confidential memory as well as MMIO, removing the dependence on para-virtualized I/O.

The AP-TEE-IO TG will work on the following deliverables; where applicable, the ABI extensions are expected to extend the AP-TEE TEE-Host/TEE-Guest ABIs:

  - A normative non-ISA ABI specification between a non-TCB (host or guest) software and an AP-TEE compliant TEE Security Manager (TSM). This interface will cover:
    - Enable  an untrusted OS/VMM to assign/revoke TEE-I/O devices to/from TVMs.
    - Enable TVMs to verify and attest to a device trustworthiness before accepting it into its TCB via the use of a Trusted Device Manager (TDM).
  - Requirements for IOMMU extensions (non-ISA) to support performant TEE-I/O devices DMA to confidential memory and secure MMIO.
  - Non-normative extensions to the AP-TEE security recommendations to describe the software flows and protocols that may be used for device attestation and updates.

The TG will work on extending the AP-TEE PoC for an open source implementation for TEE-IO. The development of the deliverables will happen in collaboration with other SIGs/TGs that the TEE-I/O framework depends on, e.g. the AP-TEE, Hypervisor and IOMMU TGs.

Device-specific and interconnect security mechanisms required to establish and maintain trust between the TVM and its assigned devices is out-of-scope for this TG. The recommendations will refer to industry-defined frameworks to address these aspects that are being developed in DMTF (CMA/SPDM), PCI-SIG (TDISP and IDE) and CXL proposed standards.
