# Container Security Governance   
   
###    
### **User Problems**   
- Figure out Container Vulnerabilities based on NIST    
- Patch usually upstream. or rebuild the entire docker based on fixed os level packages   
- Sign the patched image to attain container authenticity.   
- Store container vulnerabilities report through gitops to bring ease in audit.   
- Attain container provenance through SLSA 3    
   
   
### Unoplat Core Solution   
Distributed Container Security Analysis, Automatic Patch and Authenticity of Artifacts is implemented through combination of below tools is used to achieve the desired objective:   
  - [https://github.com/aquasecurity/trivy](https://github.com/aquasecurity/trivy)    
  - [https://github.com/project-copacetic/copa-action](https://github.com/project-copacetic/copa-action)    
  - [https://github.com/sigstore/cosign](https://github.com/sigstore/cosign)    
  - [https://github.com/unoplat/unoplat](https://github.com/unoplat/unoplat)    
  - [https://github.com/unoplat/unoplat-utilities](https://github.com/unoplat/unoplat-utilities)    
   
### TODO   
- [ ] Container provenance through BYOB in slsa dev not available yet. Integrate as soon as available.   
- [ ] Implement distributed generic DevSecOps - [https://github.com/unoplat/unoplat/blob/develop/.github/devSecOps.md](https://github.com/unoplat/unoplat/blob/develop/.github/devSecOps.md)     
   
### Status   
In Progress   
