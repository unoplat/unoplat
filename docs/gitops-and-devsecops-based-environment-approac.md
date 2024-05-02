# GitOps And DevSecOps based Environment Approach   
### **User Problems**   
- Users need to maintain different environments for different core and custom cloud native applications .   
- There is no organisation wide state to manage environments which helps them rollback/upgrade when needed based on particular artifact.   
- Also there is often dependency associated while upgrading connected components which also requires state.   
   
   
### Unoplat Core Solution   
Deploy apps automatically while maintaining state in s3 and managing dependencies through devSecOps and GitOps. This way there is complete control to install/update/uninstall apps across different environments. This will be achieved through combination of tools:   
- Unoplat CLI (ease the interaction with Unoplat DevSecOps)   
- Pulumi ( GitOps driven Environments and Dependency Management)   
- Flux (Semaless Helm Reconciliation offering canary,blue-green deployments)   
   
   
### TODO   
- [ ] Poc with Pulumi with core api and network cloud native unoplat stack. - In progess    
- [ ] Poc with flux and pulumi   
- [ ] Integrate into DevSecOps and PR   
### Status   
In Progress   
