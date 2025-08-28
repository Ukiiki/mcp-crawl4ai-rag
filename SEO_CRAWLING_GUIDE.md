# 🔍 SEO Knowledge Base Crawling Strategy

## 🎯 **Your Goal**: Create knowledge base for SEO-optimized description GPT

## 📋 **What to Crawl for SEO Descriptions**

### **1. SEO Authority Sites**
```
- https://moz.com/learn/seo
- https://ahrefs.com/blog/
- https://searchengineland.com/
- https://backlinko.com/
- https://neil-patel.com/blog/
```

### **2. Your Client's Industry Competitors**
```
- Top 5 competitor websites
- Their product/service pages
- Their category descriptions
- Their blog content about the industry
```

### **3. High-Performing Product Pages**
```
- Amazon product pages in relevant category
- Shopify stores in the niche
- Industry-leading e-commerce sites
```

### **4. Industry-Specific Resources**
```
- Trade association websites
- Industry publication sites
- Niche authority blogs
- Professional forums/communities
```

## 🛠️ **MCP Tools to Use**

### **For Single Pages**
```json
{
  "tool": "crawl_single_page",
  "url": "https://example.com/seo-guide"
}
```

### **For Entire Sites** (Recommended)
```json
{
  "tool": "smart_crawl_url", 
  "url": "https://moz.com/learn/seo",
  "max_depth": 3,
  "max_concurrent": 10
}
```

### **For Sitemaps** (Most Efficient)
```json
{
  "tool": "smart_crawl_url",
  "url": "https://example.com/sitemap.xml"
}
```

## 🎯 **Crawling Workflow for SEO GPT**

### **Phase 1: SEO Fundamentals**
1. Crawl Moz SEO Learning Center
2. Crawl Ahrefs Blog (SEO sections)
3. Crawl Search Engine Land guides

### **Phase 2: Industry-Specific Content** 
1. Crawl client's top 5 competitors
2. Focus on product/service description pages
3. Capture category and landing pages

### **Phase 3: High-Converting Examples**
1. Crawl successful e-commerce product pages
2. Look for pages with good organic rankings
3. Capture meta descriptions and product copy

### **Phase 4: Search and Test**
```json
{
  "tool": "perform_rag_query",
  "query": "how to write SEO product descriptions",
  "match_count": 10
}
```

## 📊 **Expected Knowledge Base Size**

| Content Type | Pages | Est. Chunks | Purpose |
|--------------|-------|-------------|---------|
| SEO Guides | 100-200 | 1,000-2,000 | Best practices |
| Competitor Pages | 50-100 | 500-1,000 | Industry examples |
| Product Examples | 200-500 | 2,000-5,000 | Copy templates |
| **Total** | **350-800** | **3,500-8,000** | **Complete KB** |

## 🎨 **Custom GPT Integration**

Once crawled, your GPT will be able to:

✅ **Generate SEO-optimized descriptions** based on industry best practices  
✅ **Use competitor language patterns** for authenticity  
✅ **Include relevant keywords** from successful pages  
✅ **Follow proven formatting** from high-converting examples  
✅ **Adapt tone and style** to your client's industry  

## 🚀 **Next Steps**

1. **Deploy your server** (Railway/Render)
2. **Set up Supabase** database  
3. **Start crawling** with the URLs above
4. **Test search functionality** with SEO queries
5. **Train your custom GPT** with the knowledge base

Perfect for creating professional SEO descriptions at scale! 🎯