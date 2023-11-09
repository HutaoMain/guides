**list down all from a collection**

```
  const [bmiData, setBmiData] = useState<IBMIData[]>([]);

  const bmiCollectionRef = collection(db, "bmiResult");

  useEffect(() => {
    const fetchData = async () => {
      const querySnapshot = await getDocs(bmiCollectionRef);

      const data = querySnapshot.docs.map(
        (doc) =>
          ({
            id: doc.id,
            ...doc.data(),
          } as IBMIData)
      );

      setBmiData(data as IBMIData[]);
    };
    fetchData();
  }, []);

```
