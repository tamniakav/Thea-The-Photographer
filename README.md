# Thea-The-Photographer
Just another repository
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Thea_the_Photographer
{
    class Program
    {
        static void Main(string[] args)
        {
            long pictures = int.Parse(Console.ReadLine());
            long filterTime = int.Parse(Console.ReadLine());
            long percentageFilterPictures = int.Parse(Console.ReadLine());
            long uploadTime = int.Parse(Console.ReadLine());

            long percentageFilteredPictures = (int)Math.Ceiling((pictures * percentageFilterPictures) / 100m);
            long filteredPictures = pictures * filterTime;
            long picturesForUpload = percentageFilteredPictures * uploadTime;

            long timeInSeconds = filteredPictures + picturesForUpload;

            if (timeInSeconds > 59)
            {
                long minutes = timeInSeconds / 60;
                long seconds = timeInSeconds % 60;

                if (minutes > 59)
                {
                    long hours = minutes / 60;
                    minutes = minutes % 60;

                    if (hours > 23)
                    {
                        long days = hours / 24;
                        hours = hours % 24;

                        Console.WriteLine($"{days}:{hours:d2}:{minutes:d2}:{seconds:d2}");
                    }
                    else
                    {
                        Console.WriteLine($"0:{hours:d2}:{minutes:d2}:{seconds:d2}");
                    }
                }
                else
                {
                    Console.WriteLine($"0:00:{minutes:d2}:{seconds:d2}");
                }
            }
            else
            {
                Console.WriteLine($"0:00:00:{timeInSeconds:d2}");
            }
        }
    }
}
