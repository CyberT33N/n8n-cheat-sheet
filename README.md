# n8n-cheat-sheet

# Guides

## MCP
- https://www.youtube.com/watch?v=kj4eK9ylGDk






<br><br>
________
________
<br><br>


# Installation
- xx




## **n8n Cloud vs. Self-Hosting**  

| **Kriterium**         | **n8n Cloud**                        | **Self-Hosting**                     |
|----------------------|----------------------------------|--------------------------------|
| **Setup & Wartung**  | Kein Aufwand, sofort nutzbar   | Eigenes Setup & Wartung nötig |
| **Kosten**          | Monatliche Gebühr              | Hosting-Kosten, aber keine Abo-Gebühren |
| **Performance**     | Skalierbar, aber begrenzte Ressourcen je nach Plan | Volle Kontrolle über Ressourcen |
| **Sicherheit**      | n8n übernimmt Security & Updates | Eigene Sicherheitsmaßnahmen nötig |
| **Anpassbarkeit**   | Eingeschränkte Customization   | Vollständig anpassbar |
| **Integrationen**   | Alle Standardintegrationen verfügbar | Eigene Erweiterungen & Plugins möglich |
| **Zugriff**         | Sofort weltweit erreichbar     | Eigene Server oder Cloud nötig |
| **Datenschutz**     | Daten auf n8n-Servern (EU/USA) | Volle Kontrolle über Daten & Speicherung |
| **Updates**        | Automatisch                    | Manuelle Updates erforderlich |
| **Failover & Backup** | Inklusive                      | Selbst verantwortlich |

**Fazit:**  
- **n8n Cloud**: Für schnelle, sorgenfreie Nutzung ohne Wartungsaufwand.  
- **Self-Hosting**: Für maximale Kontrolle, Datenschutz und individuelle Anpassungen.







## Self Hosting

### Hostinger






















<br><br>
________
________
<br><br>


# MCP



<details><summary>Click to expand..</summary>



# n8n-nodes-mcp
- https://github.com/nerding-io/n8n-nodes-mcp
- This is an n8n community node that allows users to interact with Model Context Protocol (MCP) servers within their n8n workflows, enabling AI models to connect with external tools and data sources.



## Install
- n8n > community nodes > enter npm package name `n8n-nodes-mcp`




<br><br>
<br><br>



### Using as a Tool


<details><summary>Click to expand..</summary>

This node can be used as a tool in n8n AI Agents. To enable community nodes as tools, you need to set the `N8N_COMMUNITY_PACKAGES_ALLOW_TOOL_USAGE` environment variable to `true`.

### Setting the Environment Variable

**If you're using a bash/zsh shell:**
```bash
export N8N_COMMUNITY_PACKAGES_ALLOW_TOOL_USAGE=true
n8n start
```

**If you're using Docker:**
Add to your docker-compose.yml file:
```yaml
environment:
  - N8N_COMMUNITY_PACKAGES_ALLOW_TOOL_USAGE=true
```

**If you're using the desktop app:**
Create a `.env` file in the n8n directory:
```
N8N_COMMUNITY_PACKAGES_ALLOW_TOOL_USAGE=true
```

**If you want to set it permanently on Mac/Linux:**
Add to your `~/.zshrc` or `~/.bash_profile`:
```bash
export N8N_COMMUNITY_PACKAGES_ALLOW_TOOL_USAGE=true
```


</details>
























<br><br>
<br><br>




## How to use
- Add first step > MCP client




<br><br>
<br><br>


## How to use MCP Client Tool

1.
- Add first step > MCP client > Tool > HTTP request tool
  - Alternative you can use aswell MCP Client Tool 

2. Choose client e.g. Firecrawl and then choose between `STDIO (run´s all the time)` or `SSE (created on demand)`

3. You can find the needed informations always in the config:
```javascript
{
  "mcpServers": {
    "mcp-server-firecrawl": {
      "command": "npx",
      "args": ["-y", "firecrawl-mcp"],
      "env": {
        "FIRECRAWL_API_KEY": "YOUR_API_KEY_HERE"
      }
    }
  }
}
```

So this means:
```plaintext
command: npx
aregs: -y firecrawl-mcp
evironments: FIRECRAWL_API_KEY=xxxxxxxxxxxx
```
- https://github.com/mendableai/firecrawl-mcp-server


All endpoints from the firecrawl api docs are available in this mcp server


4. Add tool > mcp clien tool
```
Operation: Execute Tool

Tool Name > Click expression: {{ $fromAI('tool_to_use') }}
Tool Parameter: Click button let ai modify parameter
```



  
</details>
