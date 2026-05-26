# VaxAdvisor 💉

Telegram Mini App for vaccination recommendations based on Russian National Immunization Calendar, WHO, and CDC guidelines.

## Features

- 📋 **Patient Parameter Input**: Age, sex, medical history, conditions, occupation, travel plans
- 💊 **Personalized Vaccine Recommendations**: Smart algorithm analyzes 30+ vaccines against patient profile
- 📅 **National Calendar**: Russian immunization schedule (Приказ Минздрава №1122н)
- 🩺 **Disease-Specific Schemes**: Vaccination protocols for chronic conditions, immunodeficiency, pregnancy
- 🦠 **Pathogen Database**: Comprehensive vaccine info with manufacturers, dosing, contraindications
- 🧪 **Antibody Analysis**: Interpret serological test results (anti-HBs, anti-HAV, IgG markers)
- 🌍 **Travel Planning**: Epidemiological recommendations for endemic regions
- 💾 **Cloud Storage**: Save and restore patient data via Telegram

## Tech Stack

- **Frontend**: HTML5, CSS3, Vanilla JavaScript
- **Integration**: Telegram Web App API
- **Data**: Local (no backend required currently)
- **Hosting**: Vercel, Heroku, or custom VPS

## Getting Started

### Prerequisites

- Node.js 16+ (optional, for serving locally)
- Telegram account
- Bot token from [@BotFather](https://t.me/botfather)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/Anakinra23/VaxAdvisor.git
cd VaxAdvisor
```

2. (Optional) Start a local server:
```bash
npx http-server .
```

3. Deploy to your hosting service (see [Deployment](#deployment) below)

## Deployment

### Vercel (Recommended)

```bash
npm install -g vercel
vercel
```

Following prompts will deploy your app. Use the URL in Telegram Bot settings.

### Heroku

```bash
heroku login
heroku create vaxadvisor
git push heroku main
```

## Telegram Bot Setup

1. Open [@BotFather](https://t.me/botfather)
2. `/newbot` → Create your bot
3. Copy the **Bot Token**
4. `/setmenu` → Add inline buttons
5. Set the **Mini App URL** in bot settings:
   - Use your deployed URL (e.g., `https://vaxadvisor.vercel.app`)

## API Reference

### Vaccine Data Structure

```javascript
{
  id: 'bcg',
  n: 'БЦЖ / БЦЖ-М (туберкулёз)',
  g: 'Нацкалендарь',
  i: '🔵',
  c: 1,  // c=1: in national calendar
  d: 'Description and contraindications'
}
```

### Recommendation Logic

`getRec(params)` analyzes:
- Age & sex
- Vaccination history
- Chronic conditions
- Occupational exposure
- Travel plans
- Pregnancy status

Returns: `{rec, opt, contra, notes}`

## Contributing

Contributions welcome! Areas for improvement:

- Backend API for cloud storage
- Multilingual support
- Integration with Russian medical databases
- Analytics & statistics
- Export to PDF

## License

MIT License. See LICENSE file.

## Disclaimer

⚠️ **Information only** - VaxAdvisor is an educational tool. Vaccination decisions must be made with a qualified healthcare provider. Not a substitute for medical advice.

## References

- Приказ Минздрава РФ №1122н (National Immunization Calendar)
- WHO Immunization Schedule
- CDC Vaccination Guidelines
- Russian Medical Protocols

## Contact

For issues or suggestions:
- GitHub Issues
- Telegram: [@Anakinra23](https://t.me/Anakinra23)
