# UNIBIT
using OpenQA.Selenium;
using OpenQA.Selenium.Chrome;
using System.Text;
using System.Threading;
using System.Threading.Tasks;

namespace _46094r_UKT
{
    class Program
    {
        static void Main(string[] args)
        {
            IWebDriver theDriver = new ChromeDriver();

            theDriver.Url = "https://google.com/";

            theDriver.Manage().Window.Maximize();

            theDriver.Manage().Timeouts().ImplicitWait = System.TimeSpan.FromSeconds(15);

            theDriver.FindElement(By.XPath("/html/body/div/div[3]/form/div[2]/div[1]/div[1]/div/div[2]/input")).SendKeys("YouTube" + Keys.Enter);

            theDriver.FindElement(By.TagName("h3")).Click();

            IWebElement query = theDriver.FindElement(By.Name("search_query"));

            query.SendKeys("Doom Ethernal Ost" + Keys.Enter);

            theDriver.FindElement(By.XPath("/html/body/ytd-app/div/ytd-page-manager/ytd-search/div[1]/ytd-two-column-search-results-renderer/div/ytd-section-list-renderer/div[2]/ytd-item-section-renderer/div[3]/ytd-video-renderer[1]/div[1]/div/div[1]/div/h3/a/yt-formatted-string")).Click();

            Thread.Sleep(14000);

            theDriver.Quit();
        }
    }
}

Кода много лесен със помощта на селениум отваряме Chrome в който се изписва следния линк "https://google.com/"; увеличава прозореца и въвежда "YouTube" в търсачката, а след това в търсачката search_query търси клип "Doom Ethernal Ost" и го пуска.
