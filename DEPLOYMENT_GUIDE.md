# 🚀 Crawl4AI RAG MCP Server - Deployment Guide

## 🎯 **Permanent Domain Deployment**

This guide shows you how to deploy the Crawl4AI RAG MCP Server to a **permanent domain** instead of localhost.

## 🌐 **Recommended Deployment Platforms**

### 1. **Railway** (Easiest for beginners)
```bash
# Install Railway CLI
npm install -g @railway/cli

# Login and deploy
railway login
railway deploy
```
**Result**: `https://your-app-name.railway.app`

### 2. **Render** (Great free tier)
- Connect your GitHub repo at [render.com](https://render.com)
- Select "Web Service" 
- Build command: `pip install uv && uv pip install -e . && crawl4ai-setup`
- Start command: `python src/crawl4ai_mcp.py`

**Result**: `https://your-app-name.onrender.com`

### 3. **Vercel** (Fast and reliable)
```bash
# Install Vercel CLI
npm install -g vercel

# Deploy
vercel --prod
```

### 4. **Docker + DigitalOcean/AWS**
```bash
# Build and deploy Docker image
docker build -t mcp/crawl4ai-rag .
docker run -p 8051:8051 --env-file .env mcp/crawl4ai-rag
```

## 📋 **Environment Variables for Production**

Create these environment variables in your deployment platform:

```env
# Server Configuration
TRANSPORT=sse
HOST=0.0.0.0
PORT=8051

# Required Services
OPENAI_API_KEY=sk-your-real-openai-key
SUPABASE_URL=https://your-project.supabase.co
SUPABASE_SERVICE_KEY=your-service-key

# Model Configuration
MODEL_CHOICE=gpt-4o-mini

# RAG Features (optional)
USE_CONTEXTUAL_EMBEDDINGS=false
USE_HYBRID_SEARCH=true
USE_AGENTIC_RAG=false
USE_RERANKING=true
USE_KNOWLEDGE_GRAPH=false

# Neo4j (optional - for knowledge graph)
NEO4J_URI=bolt://localhost:7687
NEO4J_USER=neo4j
NEO4J_PASSWORD=your-neo4j-password
```

## 🗄️ **Database Setup (Supabase)**

1. **Create Supabase Project**: [supabase.com/dashboard](https://supabase.com/dashboard)

2. **Run SQL Schema**: Copy content from `crawled_pages.sql` and run in SQL editor

3. **Get Credentials**:
   - **URL**: Project Settings → API → Project URL
   - **Service Key**: Project Settings → API → service_role secret

## 🔧 **MCP Client Configuration**

### For Production Domain:
```json
{
  "mcpServers": {
    "crawl4ai-rag": {
      "transport": "sse",
      "url": "https://your-domain.com/sse"
    }
  }
}
```

### For Claude Code:
```bash
claude mcp add-json crawl4ai-rag '{"type":"http","url":"https://your-domain.com/sse"}' --scope user
```

## 🚦 **Testing Your Deployment**

```bash
# Test SSE endpoint
curl https://your-domain.com/sse

# Expected response
event: endpoint
data: /messages/?session_id=...
```

## 📊 **Monitoring & Logs**

Most platforms provide:
- **Automatic scaling**
- **Built-in monitoring** 
- **Log aggregation**
- **Health checks**
- **SSL certificates** (HTTPS)

## 🔒 **Security Best Practices**

1. **Environment Variables**: Never commit API keys to Git
2. **HTTPS Only**: Use SSL/TLS certificates  
3. **Rate Limiting**: Configure if supported by platform
4. **CORS**: Configure allowed origins if needed

## 💡 **Why Permanent Domain > Localhost?**

| Localhost | Permanent Domain |
|-----------|------------------|
| ❌ Only works on your machine | ✅ Accessible from anywhere |
| ❌ Stops when you close terminal | ✅ Always running (24/7) |
| ❌ No HTTPS/SSL | ✅ Secure HTTPS by default |
| ❌ Can't share with team | ✅ Share URL with anyone |
| ❌ No automatic scaling | ✅ Scales with traffic |
| ❌ No backup/redundancy | ✅ Built-in reliability |

## 🎯 **Recommended Setup for You**

1. **Deploy to Railway/Render** (easiest start)
2. **Set up Supabase** (database + vector search)  
3. **Add OpenAI API key** (for embeddings)
4. **Test with MCP client** (Claude/Cursor)
5. **Scale up as needed** (upgrade hosting plan)

Your Crawl4AI server will then be available 24/7 at a permanent URL like:
- `https://crawl4ai-rag.railway.app`
- `https://your-crawl4ai.onrender.com` 
- `https://crawl4ai.yourdomain.com`

## 🚀 **Next Steps**

1. Choose a deployment platform above
2. Set up environment variables
3. Deploy your code
4. Configure your MCP client with the new URL
5. Start crawling and building your knowledge base!

The server will be **permanently accessible** and ready to serve your AI coding assistants! 🎉