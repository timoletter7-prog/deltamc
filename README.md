# Delta MC Website

A modern React-based website for Delta MC Minecraft server featuring shop, events, and Supabase-powered purchases.

## Features

- 🛒 **Shopping Cart**: Full e-commerce functionality with cart management
- 🎯 **Shop Items**: Ranks (VIP, MVP, Elite) and crate keys
- 💳 **Checkout System**: Complete purchase flow with Supabase integration
- 📊 **Purchase Processing**: Automatic order fulfillment via Minecraft plugin
- 🎨 **Modern UI**: Built with shadcn/ui components and Tailwind CSS
 
## Setup

### Frontend Setup

1. Install dependencies:
```bash
npm install
```

2. Configure Supabase:
```bash
cp .env.example .env
# Edit .env with your Supabase credentials (already configured)
```

3. Start development server:
```bash
npm run dev
```

4. Build for production:
```bash
npm run build
```

### Minecraft Plugin Setup

1. Build the plugin:
```bash
cd plugin-api/plugin
mvn clean package
```

2. Copy the JAR file to your Minecraft server's plugins folder

3. Configure the plugin in `config.yml`:
```yaml
api-port: 8080  # Port for the HTTP API
```

4. Restart your Minecraft server

## Environment Variables

| Variable | Description | Default |
|----------|-------------|---------|
| `VITE_SUPABASE_URL` | Supabase project URL | `https://wkbmjhoxfaomukzvhmbf.supabase.co` |
| `VITE_SUPABASE_ANON_KEY` | Supabase anonymous key | `eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...` |

## API Endpoints

The Minecraft plugin exposes:
- `GET /online` - Returns current online player count

## Deployment

1. Build the frontend: `npm run build`
2. Deploy the `dist/` folder to your web server
3. Ensure the Minecraft plugin is running and accessible
4. Configure CORS if needed in the plugin

## Tech Stack

- **Frontend**: React, TypeScript, Vite, Tailwind CSS, shadcn/ui
- **Backend**: Java (Minecraft Plugin), Spark Framework
- **State Management**: React Context, TanStack Query
