# Api and Network Security   
### **User Problems**   
- Users need seamless north south and east west traffic encryption , Load balancing, Observability etc with DNS of cloud native environments.   
- Users need to research to land on right oss toolset, configure, implement cross cutting concerns such as observability, scalability, fault tolerance and high availability across all components.   
- Users need to research and understand best devSecOps and GitOps practices to manage environments core needs reliably.   
   
   
### Unoplat Core Solution   
[Cross Cutting Concerns for Core Components](cross-cutting-concerns-for-core-components.md)    
R&D to land on below unoplat components:   
  - Linkerd For Service Mesh   
  - Ambassador for Api Gateway   
  - letsEncrypt to act as CA based on user domain to auto generate and rotate root certs   
  - Cert Manager to rotate intermediate certs   
   
     
### TODO   
- [x] Cert and Linkerd POc   
- [ ] Integrated POC for all components   
   
### Status   
In Progress   
