# 🗄️ Supabase Database Setup for SEO Knowledge Base

## Quick Setup (10 minutes)

### 1. Create Supabase Project
1. Go to [supabase.com/dashboard](https://supabase.com/dashboard)
2. Click **"New Project"**
3. Choose organization and give it a name: `seo-knowledge-base`
4. Choose region closest to your users
5. Generate a strong password
6. Click **"Create new project"**

### 2. Get Your Credentials
Once project is created:
- **Project URL**: Project Settings → API → Project URL
- **Service Key**: Project Settings → API → `service_role` secret (starts with `eyJ...`)

### 3. Run Database Schema
1. Go to **SQL Editor** in Supabase dashboard
2. Click **"New query"**
3. Copy and paste the entire content from `crawled_pages.sql`
4. Click **"Run"** 

✅ This creates all tables and functions needed for vector search.

### 4. Verify Setup
Check these tables were created:
- `sources` - Tracks crawled websites
- `crawled_pages` - Stores content chunks with embeddings  
- `code_examples` - Stores code snippets (optional)

## 🎯 For Your SEO Use Case

Your knowledge base will store:
- **Website content** → Chunked and searchable
- **SEO best practices** → From crawled SEO resources
- **Product descriptions** → Examples from competitor sites
- **Industry terminology** → Domain-specific language

Perfect for training your custom GPT! 🚀